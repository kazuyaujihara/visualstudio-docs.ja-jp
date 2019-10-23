---
title: IIS コンピューター上の ASP.NET のリモート デバッグ
ms.custom:
- remotedebugging
- seodec18
ms.date: 05/21/2018
ms.topic: conceptual
ms.assetid: 9cb339b5-3caf-4755-aad1-4a5da54b2a23
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 86b035164c4d34f4ce0182ea51fdfe6381ad2d4f
ms.sourcegitcommit: 08c144d290da373df841f04fc799e3133540a541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72536024"
---
# <a name="remote-debug-aspnet-on-a-remote-iis-computer"></a>リモートの IIS コンピューター上の ASP.NET のリモート デバッグ
IIS に配置されている ASP.NET アプリケーションをデバッグするには、アプリを配置したコンピューターにリモートツールをインストールして実行し、Visual Studio から実行中のアプリにアタッチします。

![リモートデバッガーコンポーネント](../debugger/media/remote-debugger-aspnet.png "Remote_debugger_components")

このガイドでは、Visual Studio ASP.NET MVC 4.5.2 アプリケーションをセットアップして構成し、IIS に配置して、リモートデバッガーを Visual Studio からアタッチする方法について説明します。

> [!NOTE]
> 代わりに、リモートデバッグ ASP.NET Core については、「 [IIS コンピューター上のリモートデバッグ ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)」を参照してください。 Azure App Service の場合、[スナップショットデバッガー](../debugger/debug-live-azure-applications.md) (.net 4.6.1 required) を使用するか、[サーバーエクスプローラーからデバッガーをアタッチ](../debugger/remote-debugging-azure.md)することによって、構成済みの IIS インスタンスで簡単にデプロイおよびデバッグできます。

## <a name="prerequisites"></a>必要条件

::: moniker range=">=vs-2019"
この記事に記載されている手順を実行するには、Visual Studio 2019 が必要です。
::: moniker-end
::: moniker range="vs-2017"
この記事に記載されている手順を実行するには、Visual Studio 2017 が必要です。
::: moniker-end

これらの手順は、次のサーバー構成でテストされています。
* Windows Server 2012 R2 および IIS 8 (Windows Server 2008 R2 の場合、サーバーの手順は異なります)

## <a name="network-requirements"></a>ネットワーク要件

リモートデバッガーは、windows server 2008 Service Pack 2 以降の Windows Server でサポートされています。 要件の完全な一覧については、「[要件](../debugger/remote-debugging.md#requirements_msvsmon)」を参照してください。

> [!NOTE]
> プロキシ経由で接続されている2台のコンピューター間のデバッグはサポートされていません。 高待機時間または低帯域幅の接続 (ダイヤルアップインターネット、または複数の国にまたがるインターネットなど) でのデバッグは推奨されておらず、失敗したり、非常に時間がかかる場合があります。

## <a name="app-already-running-in-iis"></a>アプリは既に IIS で実行されていますか?

この記事では、Windows server で IIS の基本的な構成を設定し、Visual Studio からアプリをデプロイする手順について説明します。 これらの手順は、サーバーに必要なコンポーネントがインストールされていること、アプリが正常に実行できること、およびリモートデバッグの準備ができていることを確認するために含まれています。

* アプリが IIS で実行されていて、リモートデバッガーをダウンロードしてデバッグを開始するだけの場合は、「 [Windows Server でのリモートツールのダウンロードとインストール](#BKMK_msvsmon)」を参照してください。

* アプリケーションをデバッグできるように IIS で正しくセットアップ、展開、および実行するためのヘルプが必要な場合は、このトピックのすべての手順に従ってください。

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>Visual Studio コンピューターで ASP.NET 4.5.2 アプリケーションを作成する

1. MVC の ASP.NET アプリケーションを新規作成します。

    ::: moniker range=">=vs-2019"
    Visual Studio 2019 で、 **Ctrl キーを押しながら Q キーを押し**て検索ボックスを開き、「 **asp.net**」と入力します。次に、 **[テンプレート]** を選択し、[**新しい ASP.NET Web アプリケーションの作成] (.NET Framework)** を選択します。 表示されるダイアログボックスで、プロジェクトに**MyASPApp**という名前を指定し、 **[作成]** を選択します。 **[MVC]** を選択し、 **[作成]** を選択します。
    ::: moniker-end
    ::: moniker range="vs-2017"
    Visual Studio 2017 でこれを行うには、 **[ファイル > 新しい > プロジェクト]** を選択し、 **[visual C# > web > ASP.NET web アプリケーション]** を選択します。 **[ASP.NET 4.5.2** テンプレート] セクションで、 **[MVC]** を選択します。 **[Docker サポートを有効に]** する が選択されておらず、**認証**が **[認証なし]** に設定されていることを確認します。 プロジェクトに**MyASPApp**という名前を指定します。)
    ::: moniker-end

2. *HomeController.cs*ファイルを開き、`About()` メソッドにブレークポイントを設定します。

## <a name="bkmk_configureIIS"></a>Windows Server に IIS をインストールして構成する

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server でブラウザーのセキュリティ設定を更新する

Internet Explorer で [セキュリティ強化の構成] が有効になっている場合 (既定では有効になっています)、一部のドメインを信頼済みサイトとして追加して、一部の web サーバーコンポーネントをダウンロードできるようにする必要があります。 信頼済みサイトを追加するには、[**インターネットオプション] > [セキュリティ > 信頼済みサイト > サイト**] の順に移動します。 次のドメインを追加します。

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- iis.net

ソフトウェアをダウンロードするときに、さまざまな web サイトのスクリプトとリソースを読み込むためのアクセス許可を付与するように求められる場合があります。 これらのリソースの一部は必須ではありませんが、プロセスを簡略化するために、メッセージが表示されたら **[追加]** をクリックします。

## <a name="BKMK_deploy_asp_net"></a>Windows Server に ASP.NET 4.5 をインストールする

IIS に ASP.NET をインストールするための詳細な情報が必要な場合は、 [ASP.NET 3.5 と ASP.NET 4.5 を使用した iis 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)を参照してください。

1. サーバーマネージャーの左側のウィンドウで、 **[IIS]** を選択します。 サーバーを右クリックして **[インターネット インフォメーション サービス (IIS) マネージャー]** を選択します。

1. Web Platform Installer (WebPI) を使用して、ASP.NET 4.5 をインストールします (Windows Server 2012 R2 のサーバーノードから、 **[新しい Web プラットフォームコンポーネントの取得]** を選択し、ASP.NET を検索します)。

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Windows Server 2008 R2 を使用している場合は、次のコマンドを使用して ASP.NET 4 をインストールします。

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. システムを再起動します (または、コマンド プロンプトから **net stop was /y** の後に続けて **net start w3svc** を実行して、システム PATH への変更を適用します)。

## <a name="choose-a-deployment-option"></a>デプロイオプションの選択

IIS へのアプリの展開に関するヘルプが必要な場合は、次のオプションを検討してください。

* IIS で発行設定ファイルを作成し、Visual Studio で設定をインポートしてデプロイします。 シナリオによっては、これはアプリをデプロイするための迅速な方法です。 発行設定ファイルを作成すると、IIS でアクセス許可が自動的に設定されます。

* ローカルフォルダーに発行し、推奨される方法で出力を IIS 上の準備済みアプリフォルダーにコピーして配置します。

## <a name="optional-deploy-using-a-publish-settings-file"></a>Optional発行設定ファイルを使用したデプロイ

このオプションを使用して、発行設定ファイルを作成し、Visual Studio にインポートすることができます。

> [!NOTE]
> この展開方法では、Web 配置を使用します。 設定をインポートするのではなく、Visual Studio で Web 配置手動で構成する場合は、ホスティングサーバー用に 3.6 Web 配置ではなく Web 配置3.6 をインストールできます。 ただし、Web 配置を手動で構成する場合は、サーバー上のアプリフォルダーに正しい値とアクセス許可が構成されていることを確認する必要があります ( [ASP.NET Web サイトの構成](#BKMK_deploy_asp_net)に関するページを参照してください)。

### <a name="install-and-configure-web-deploy-for-hosting-servers-on-windows-server"></a>Windows Server でサーバーをホストするための Web 配置のインストールと構成

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

### <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Windows Server 上の IIS に発行設定ファイルを作成する

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/create-publish-settings-iis.md)]

### <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio で発行設定をインポートして配置する

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/import-publish-settings-vs.md)]

アプリが正常に配置されたら、自動的に起動されます。 アプリが Visual Studio から起動しない場合は、IIS でアプリを起動します。

1. **[設定]** ダイアログボックスで、 **[次へ]** をクリックしてデバッグを有効にし、**デバッグ**構成を選択します。次に、 **[ファイルの発行]** オプションで、 **[変換先の追加ファイルを削除]** する を選択します。

    > [!NOTE]
    > リリース構成を選択した場合は、発行時に*web.config ファイルで*デバッグを無効にします。

1. **[保存]** をクリックし、アプリを再発行します。

## <a name="optional-deploy-by-publishing-to-a-local-folder"></a>Optionalローカルフォルダーへの発行による配置

Powershell または RoboCopy を使用してアプリを IIS にコピーする場合、または手動でファイルをコピーする場合は、このオプションを使用してアプリをデプロイできます。

### <a name="BKMK_deploy_asp_net"></a>Windows Server コンピューターで ASP.NET Web サイトを構成する

1. エクスプローラーを開き、新しいフォルダー **C:\ Publish**を作成します。このフォルダーには、後で ASP.NET プロジェクトを配置します。

2. まだ開いていない場合は、**インターネットインフォメーションサービス (IIS) マネージャー**を開きます。 (サーバーマネージャーの左側のウィンドウで、 **[IIS]** を選択します。 サーバーを右クリックして **[インターネット インフォメーション サービス (IIS) マネージャー]** を選択します。)

3. 左側のウィンドウの **[接続]** で、 **[サイト]** に移動します。

4. **[既定の Web サイト]** を選択し、 **[基本設定]** を選択して、**物理パス**を**c:\ Publish**に設定します。

5. **[既定の Web サイト]** ノードを右クリックして、 **[アプリケーションの追加]** を選択します。

6. **[エイリアス]** フィールドを**MyASPApp**に設定し、既定のアプリケーションプール (**DefaultAppPool**) をそのまま使用して、**物理パス**を**c:\ Publish**に設定します。

7. **[接続]** で **[アプリケーションプール]** を選択します。 **DefaultAppPool**を開き、[アプリケーションプール] フィールドを**ASP.NET v 4.0**に設定します (ASP.NET 4.5 はアプリケーションプールのオプションではありません)。

8. IIS マネージャーでサイトを選択した状態で、 **[アクセス許可の編集]** を選択し、IUSR、IIS_IUSRS、またはアプリケーションプール用に構成されたユーザーが、読み取り & 実行権限を持つ承認済みユーザーであることを確認します。 これらのユーザーのいずれも存在しない場合は、読み取り & 実行権限を持つユーザーとして IUSR を追加します。

### <a name="publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>Visual Studio からローカルフォルダーに発行してアプリを発行してデプロイする

また、ファイルシステムまたはその他のツールを使用して、アプリを発行してデプロイすることもできます。

1. (ASP.NET 4.5.2)Web.config ファイルに正しいバージョンの .NET が表示されていることを確認します。  たとえば、ASP.NET 4.5.2 を対象としている場合は、このバージョンが web.config に表示されていることを確認します。

    ```xml
    <system.web>
      <compilation debug="true" targetFramework="4.5.2" />
      <httpRuntime targetFramework="4.5.2" />
      <httpModules>
        <add name="ApplicationInsightsWebTracking" type="Microsoft.ApplicationInsights.Web.ApplicationInsightsHttpModule, Microsoft.AI.Web" />
      </httpModules>
    </system.web>

    ```

    たとえば、4.5.2 の代わりに ASP.NET 4 をインストールした場合、バージョンは4.0 である必要があります。

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

## <a name="BKMK_msvsmon"></a>Windows Server でのリモートツールのダウンロードとインストール

使用している Visual Studio のバージョンに対応するバージョンのリモートツールをダウンロードします。

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

## <a name="BKMK_setup"></a>Windows Server でリモートデバッガーを設定する

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> 追加のユーザーにアクセス許可を追加する必要がある場合、リモートデバッガーの認証モードまたはポート番号を変更するには、「[リモートデバッガーの構成](../debugger/remote-debugging.md#configure_msvsmon)」を参照してください。

リモートデバッガーをサービスとして実行する方法の詳細については、「[サービスとしてのリモートデバッガーの実行](../debugger/remote-debugging.md#bkmk_configureService)」を参照してください。

## <a name="BKMK_attach"></a> Visual Studio コンピューターから ASP.NET アプリケーションにアタッチする

1. Visual Studio コンピューターで、デバッグしようとしているソリューションを開きます (この記事の手順に従っている場合は**MyASPApp** )。
2. Visual Studio で、**デバッグ > プロセスにアタッチ** をクリックします (Ctrl + Alt + P)。

    > [!TIP]
    > Visual Studio 2017 以降のバージョンでは、**デバッグ > プロセスに再アタッチ** (Shift + Alt + P) を使用して、以前にアタッチしたのと同じプロセスに再アタッチできます。

3. [修飾子] フィールドを **\<remote コンピューター名 >** に設定し、 **enter**キーを押します。

    Visual Studio によって、必要なポートがコンピューター名に追加されていることを確認します。これは、 **\<remote コンピューター名 >:p ort**の形式で表示されます。

    ::: moniker range=">=vs-2019"
    Visual Studio 2019 で **\<remote コンピューター名 >: 4024**が表示されるはずです。
    ::: moniker-end
    ::: moniker range="vs-2017"
    Visual Studio 2017 で **\<remote コンピューター名 >: 4022**が表示されるはずです。
    ::: moniker-end
    ポートが必要です。 ポート番号が表示されない場合は、手動で追加します。

4. **[最新の情報に更新]** をクリックします。
    **[選択可能なプロセス]** ウィンドウにプロセスがいくつか表示されます。

    プロセスが表示されない場合は、リモートコンピューター名ではなく IP アドレスを使用してください (ポートが必要です)。 コマンドラインで `ipconfig` を使用すると、IPv4 アドレスを取得できます。

5. **[すべてのユーザーからのプロセスを表示する]** をオンにします。

6. プロセス名の最初の文字を入力して、ASP.NET 4.5 の w3wp.exe を**すばやく見つけます**。

    W3wp.exe を表示しているプロセスが複数ある場合は、[**ユーザー名** **] 列を確認**します。 場合によっては、 **[ユーザー名]** 列に、 **IIS APPPOOL\DefaultAppPool**などのアプリケーションプール名が表示されます。 アプリケーションプールが表示されている場合、適切なプロセスを簡単に識別するには、デバッグするアプリインスタンスの新しい名前付きアプリプールを作成します。その後、 **[ユーザー名]** 列で簡単に見つけることができます。

    ::: moniker range=">=vs-2019"
    ![RemoteDBG_AttachToProcess](../debugger/media/vs-2019/remotedbg-attachtoprocess.png "RemoteDBG_AttachToProcess")
    ::: moniker-end
    ::: moniker range="vs-2017"
    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg-attachtoprocess.png "RemoteDBG_AttachToProcess")
    ::: moniker-end

7. **[アタッチ]** をクリックします

8. リモート コンピューターの Web サイトを開きます。 ブラウザーで、**http://\<リモート コンピューター名>** に移動します。

    ASP.NET の Web ページが表示されるはずです。
9. 実行中の ASP.NET アプリケーションで、 **[バージョン情報]** ページへのリンクをクリックします。

    Visual Studio で、ブレークポイントにヒットするはずです。

## <a name="bkmk_openports"></a> トラブルシューティングWindows Server で必要なポートを開く

ほとんどのセットアップでは、ASP.NET とリモートデバッガーのインストールによって必要なポートが開かれます。 ただし、ポートが開いていることを確認する必要がある場合もあります。

> [!NOTE]
> Azure VM では、[ネットワークセキュリティグループ](/azure/virtual-machines/windows/nsg-quickstart-portal)を介してポートを開く必要があります。

必要なポート:

* 80-IIS で必要
::: moniker range=">=vs-2019"
* 4024-Visual Studio 2019 からのリモートデバッグに必要です (詳細については、「[リモートデバッガーのポートの割り当て](../debugger/remote-debugger-port-assignments.md)」を参照してください)。
::: moniker-end
::: moniker range="vs-2017"
* 4022-Visual Studio 2017 からのリモートデバッグに必要です (詳細については、「[リモートデバッガーのポートの割り当て](../debugger/remote-debugger-port-assignments.md)」を参照してください)。
::: moniker-end
* UDP 3702-(省略可能) 探索ポートを使用すると、Visual Studio でリモートデバッガーにアタッチするときに **[検索]** ボタンを使用できます。

1. Windows Server でポートを開くには、 **[スタート]** メニューを開き、 **[セキュリティが強化された windows ファイアウォール**] を検索します。

2. 次に、**受信の規則 > 新しい規則 > ポート** を選択します。 **[次へ]** を選択し、 **[特定のローカルポート]** でポート番号を入力し、 **[次へ]** をクリックして**接続を許可**し、[次へ] をクリックして、受信の規則の名前 (**IIS**、 **Web 配置**、または**msvsmon**) を追加します。

    Windows ファイアウォールの構成の詳細については、「 [Windows ファイアウォールをリモートデバッグ用に構成](../debugger/configure-the-windows-firewall-for-remote-debugging.md)する」を参照してください。

3. その他の必要なポートに対して追加のルールを作成します。
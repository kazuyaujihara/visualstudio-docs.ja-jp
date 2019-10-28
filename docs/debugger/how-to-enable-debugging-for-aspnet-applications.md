---
title: ASP.NET apps のデバッグを有効にする |Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications
- Web.config configuration file, debug mode
- debugging [Visual Studio], ASP.NET
ms.assetid: 3beed819-cece-4864-8184-bd410000973a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: a6f20a2272214a525b00ebf07ebc6e5e803b138c
ms.sourcegitcommit: 257fc60eb01fefafa9185fca28727ded81b8bca9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2019
ms.locfileid: "72911352"
---
# <a name="debug-aspnet-or-aspnet-core-apps-in-visual-studio"></a>Visual Studio での ASP.NET または ASP.NET Core アプリのデバッグ

Visual Studio では、ASP.NET アプリと ASP.NET Core アプリをデバッグできます。 このプロセスは、ASP.NET と ASP.NET Core と、IIS Express またはローカルの IIS サーバーのどちらで実行するかによって異なります。

>[!NOTE]
>次の手順と設定は、ローカルサーバー上のアプリをデバッグする場合にのみ適用されます。 リモート IIS サーバー上のアプリをデバッグ**するには、[プロセスにアタッチ**] を使用し、これらの設定は無視します。 IIS での ASP.NET アプリのリモートデバッグの詳細および手順については、「リモートデバッグの[ASP.NET on a iis computer](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md) 」または「remote [debug ASP.NET CORE on remote iis computer](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)」を参照してください。

組み込みの IIS Express サーバーは、Visual Studio に含まれています。 IIS Express は、ASP.NET および ASP.NET Core プロジェクトの既定のデバッグサーバーであり、事前に構成されています。 これは最も簡単なデバッグ方法であり、最初のデバッグとテストに最適です。

アプリを実行するように構成されているローカル IIS サーバー (バージョン8.0 以降) で、ASP.NET または ASP.NET Core アプリをデバッグすることもできます。 ローカル IIS でデバッグするには、次の要件を満たしている必要があります。

<a name="iis"></a>
- Visual Studio をインストールするときに、 **[開発時 IIS サポート]** を選択します。 (必要に応じて、Visual Studio インストーラーを再実行し、 **[変更]** を選択して、このコンポーネントを追加します)。
- Visual Studio を管理者として実行している。
- ASP.NET や ASP.NET Core の適切なバージョンで IIS をインストールして正しく構成します。 詳細と手順については、 [ASP.NET 3.5 と ASP.NET 4.5 を使用した iis 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) 、および[iis を使用した Windows でのホスト ASP.NET Core](/aspnet/core/host-and-deploy/iis/index)に関する説明を参照してください。
- アプリケーションが IIS でエラーなしで実行されていることを確認します。

## <a name="debug-aspnet-apps"></a>ASP.NET アプリのデバッグ

IIS Express が既定であり、事前に構成されています。 ローカル IIS でデバッグしている場合は、[ローカル iis デバッグの要件](#iis)を満たしていることを確認してください。

1. Visual**ソリューションエクスプローラー** Studio で ASP.NET プロジェクトを選択し、 **[プロパティ]** アイコンをクリックし、 **Alt**キーを押し+**enter**キーを押すか、右クリックして **[プロパティ]** を選択します。

1. **[Web]** タブを選択します。

1. **[プロパティ]** ウィンドウの **[サーバー]** の下で、
   - IIS Express には、ドロップダウンから **[IIS Express]** を選択します。
   - ローカル IIS の場合
     1. ドロップダウンから **[ローカル IIS]** を選択します。
     1. IIS でまだアプリを設定していない場合は、 **[プロジェクトの URL]** フィールドの横にある **[仮想ディレクトリの作成]** を選択します。

1. **[デバッガー]** で、 **[ASP.NET]** を選択します。

   ![ASP.NET デバッガーの設定](media/dbg-aspnet-enable-debugging2.png "ASP.NET デバッガーの設定")

1. **ファイル** > 使用**して、選択した項目を保存**するか、 **Ctrl**+**S**を使用して変更を保存します。

1. アプリをデバッグするには、プロジェクトで、いくつかのコードにブレークポイントを設定します。 Visual Studio のツールバーで、構成が **[デバッグ]** に設定されていることを確認し、必要なブラウザーが**IIS Express (\<ブラウザー名 >)** または**ローカル IIS (\<ブラウザー名 >)** に [エミュレーター] フィールドに表示されていることを確認します。

1. デバッグを開始するには、ツールバーの [ **IIS Express] (\<ブラウザー名 >)** または**ローカル IIS (\<ブラウザー名 >)** を選択し、 **[デバッグ]** メニューの **[デバッグの開始]** をクリックするか、 **F5**キーを押します。 デバッガーはブレークポイントで一時停止します。 デバッガーがブレークポイントに到達できない場合は、「[デバッグのトラブルシューティング](#troubleshoot-debugging)」を参照してください。

## <a name="debug-aspnet-core-apps"></a>ASP.NET Core アプリのデバッグ

IIS Express が既定であり、事前に構成されています。 ローカル IIS でデバッグしている場合は、[ローカル iis デバッグの要件](#iis)を満たしていることを確認してください。

1. Visual Studio**ソリューションエクスプローラー**で ASP.NET Core プロジェクトを選択し、 **[プロパティ]** アイコンをクリックして、 **Alt**+**enter**キーを押すか、右クリックして **[プロパティ]** を選択します。

1. **[デバッグ]** タブを選択します。

1. **[プロパティ]** ウィンドウで、 **[プロファイル]** の横にある
   - IIS Express には、ドロップダウンから **[IIS Express]** を選択します。
   - ローカル IIS の場合は、ドロップダウンからアプリ名を選択するか、[**新規**作成] を選択して新しいプロファイル名を作成し、[ **OK]** を選択します。

1. **[起動]** の横で、ドロップダウンリストから **[IIS Express]** または **[IIS]** を選択します。

1. **起動ブラウザー**が選択されていることを確認します。

1. **[環境変数]** で、 **ASPNETCORE_ENVIRONMENT**に " **Development**" という値が含まれていることを確認します。 それ以外の場合は、 **[追加]** を選択して追加します。

   ![デバッガー設定の ASP.NET Core](../debugger/media/dbg-aspnet-enable-debugging3.png "デバッガー設定の ASP.NET Core")

1. **ファイル** > 使用**して、選択した項目を保存**するか、 **Ctrl**+**S**を使用して変更を保存します。

1. アプリをデバッグするには、プロジェクトで、いくつかのコードにブレークポイントを設定します。 Visual Studio のツールバーで、構成が **[デバッグ]** に設定されていること、 **IIS Express**または新しい IIS プロファイル名のいずれかが [エミュレーター] フィールドに表示されていることを確認します。

1. デバッグを開始するには、ツールバーの **[IIS Express]** または [ **IIS プロファイル > 名の\<** ] を選択し、 **[デバッグ]** メニューの **[デバッグの開始]** を選択するか、 **F5**キーを押します。 デバッガーはブレークポイントで一時停止します。 デバッガーがブレークポイントに到達できない場合は、「[デバッグのトラブルシューティング](#troubleshoot-debugging)」を参照してください。

## <a name="troubleshoot-debugging"></a>デバッグのトラブルシューティング

ローカル IIS デバッグがブレークポイントに進行できない場合は、次の手順に従ってトラブルシューティングを行います。

1. IIS から web アプリを起動し、正常に動作することを確認します。 Web アプリを実行したままにします。

2. Visual Studio で、**デバッグ > プロセスにアタッチ** を選択するか、 **Ctrl**+**Alt**+**P**キーを押して、ASP.NET**または**ASP.NET Core プロセス (通常は w3wp.exe または**dotnet**) に接続します。 詳細については、「[プロセスにアタッチ](attach-to-running-processes-with-the-visual-studio-debugger.md)」と「 [ASP.NET プロセスの名前を検索する方法](how-to-find-the-name-of-the-aspnet-process.md)」を参照してください。

**[プロセスにアタッチ]** を使用してブレークポイントに接続してヒットしたが、デバッグ >  **[デバッグの開始]** または**F5** **を使用し**て実行できない場合は、プロジェクトのプロパティで設定が間違っている可能性があります。 HOSTS ファイルを使用する場合は、それも正しく構成されていることを確認してください。

## <a name="configure-debugging-in-the-webconfig-file"></a>Web.config ファイルでデバッグを構成する

ASP.NET プロジェクトには、既定で web.config ファイルがあります。このファイルには、アプリケーション構成と起動情報 (デバッグ設定を含む) の両方が含まれ*ています*。 Web.config*ファイルは*、デバッグ用に正しく構成されている必要があります。 前のセクションの**プロパティ**設定によって*web.config*ファイルが更新されますが、手動で構成することもできます。

> [!NOTE]
> ASP.NET Core プロジェクトには、最初*は web.config ファイルが*ありませんが、アプリの構成と起動情報には、 *Appsettings*ファイルと*launchsettings. json*ファイルを使用します。 アプリを配置すると、プロジェクトに*web.config ファイルが*作成されますが、通常、デバッグ情報は含まれません。

> [!TIP]
> 配置プロセス*で web.config の設定が*更新される可能性があるため、デバッグを試行する前に、web.config がデバッグ用に*構成され*ていることを確認してください。

**デバッグ用に web.config*ファイルを*手動で構成するには、次のようにします。**

1. Visual Studio で、ASP.NET プロジェクトの*web.config*ファイルを開きます。

2. *Web.config は XML*ファイルであるため、タグでマークされた入れ子のセクションが含まれています。 `configuration/system.web/compilation` セクションを見つけます。 (`compilation` 要素が存在しない場合は作成します)。

3. `compilation` 要素の `debug` 属性が `true`に設定されていることを確認します。 (`compilation` 要素に `debug` 属性が含まれていない場合は、それを追加して `true`に設定します)。

   既定の IIS Express サーバーではなくローカル IIS を使用している場合は、`compilation` 要素の `targetFramework` 属性値が IIS サーバーのフレームワークと一致していることを確認してください。

   *Web.config ファイルの*`compilation` 要素は、次の例のようになります。

   > [!NOTE]
   > この例は *、部分的な web.config ファイル*です。 通常、`configuration` 要素と `system.web` 要素には追加の XML セクションがあり、`compilation` 要素には他の属性や要素が含まれる場合もあります。

   ```xml
   <configuration>
      ...
      <system.web>
          <compilation  debug="true"  targetFramework="4.6.1" ... >
             ...
          </compilation>
      </system.web>
   </configuration>
   ```

*web.config* ファイルに変更が加えられると、[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] によってその変更が自動的に検出され、新しい構成設定が適用されます。 変更を有効にするために、コンピューターまたは IIS サーバーを再起動する必要はありません。

*Web*サイトには、複数の仮想ディレクトリとサブディレクトリを含めることができ、それぞれに web.config ファイルが含まれています。 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] アプリは、URL パスの上位レベルにある web.config ファイルから構成設定を継承*します。* 階層の*web.config*ファイルの設定は、階層内の下位にあるすべての [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] アプリに適用されます。 階層の下位にある web.config*ファイルで*別の構成を設定すると、上位のファイルの設定が上書きされます。

たとえば、 <em>www.microsoft.com/aaa/web.config</em>で `debug="true"` を指定した場合、 *aaa*フォルダーまたは*aaa*のサブフォルダー内のすべてのアプリは、その設定を継承し*ます。* ただし、これらのアプリのいずれかが独自の web.config で設定をオーバーライドする場合を除きます。拡張子.

## <a name="publish-in-debug-mode-using-the-file-system"></a>ファイルシステムを使用したデバッグモードでの発行

IIS にアプリを発行するには、さまざまな方法があります。 次の手順は、ファイルシステムを使用してデバッグ発行プロファイルを作成し、デプロイする方法を示しています。 これを行うには、Visual Studio を管理者として実行している必要があります。

> [!IMPORTANT]
> コードを変更するか、リビルドする場合は、これらの手順を繰り返して再発行する必要があります。

1. Visual Studio で、プロジェクトを右クリックし、 **[発行]** を選択します。

3. [ **IIS]、[FTP]** などを選択し、 **[発行]** をクリックします。

    ![IIS に発行する](media/dbg-aspnet-local-iis.png "IIS に公開する")

4. **[Customprofile]** ダイアログで、 **[発行方法]** の **[ファイルシステム]** を選択します。

5. **[ターゲットの場所]** で、 **[参照]** ( **...** ) を選択します。

   - ASP.NET の場合、 **[ローカル IIS]** を選択し、アプリ用に作成した web サイトを選択して、 **[開く]** を選択します。

     ![IIS への ASP.NET への発行](media/dbg-aspnet-local-iis1.png "ASP.NET を IIS に発行する")

   - ASP.NET Core で、**ファイルシステム** を選択し、アプリ用に設定したフォルダーを選択して、**開く** を選択します。

1. **[次へ]** を選択します。

1. **[構成]** で、ドロップダウンから **[デバッグ]** を選択します。

1. **[保存]** を選択します。

1. **[発行]** ダイアログで、 **customprofile** (または先ほど作成したプロファイルの名前) が表示され、 **Lastused buildconfiguration**が**Debug**に設定されていることを確認します。

1. **[発行]** を選びます。

    ![IIS に発行する](media/dbg-aspnet-local-iis-select-site.png "IIS に公開する")

> [!IMPORTANT]
> デバッグモードでは、アプリのパフォーマンスが大幅に低下します。 最適なパフォーマンスを得るには、web.config で `debug="false"` を設定し、運用アプリをデプロイするとき、またはパフォーマンス測定を実行するときにリリースビルドを*指定します*。

## <a name="see-also"></a>関連項目
- [ASP.NET のデバッグ : システム要件](aspnet-debugging-system-requirements.md)
- [方法 : ユーザー アカウントでワーカー プロセスを実行する](how-to-run-the-worker-process-under-a-user-account.md)
- [方法 : ASP.NET プロセスの名前を見つける](how-to-find-the-name-of-the-aspnet-process.md)
- [配置した Web アプリケーションのデバッグ](debugging-deployed-web-applications.md)
- [チュートリアル: Web フォームのデバッグ](walkthrough-debugging-a-web-form.md)
- [方法 : ASP.NET の例外をデバッグする](how-to-debug-aspnet-exceptions.md)
- [Web アプリケーションをデバッグする: エラーおよびトラブルシューティング](debugging-web-applications-errors-and-troubleshooting.md)

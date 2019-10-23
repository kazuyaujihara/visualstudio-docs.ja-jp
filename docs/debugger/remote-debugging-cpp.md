---
title: プロジェクトのC++リモートデバッグ |Microsoft Docs
ms.custom: remotedebugging
ms.date: 08/14/2018
ms.topic: conceptual
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 8b8eca0d-122f-4eda-848a-cf0945f207d0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 2b9cd6f120d5699464c9e7311721898a727bf47e
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72450427"
---
# <a name="remote-debugging-a-c-project-in-visual-studio"></a>Visual Studio でC++のプロジェクトのリモートデバッグ
別のコンピューターで Visual Studio アプリケーションをデバッグするには、アプリを配置するコンピューターにリモートツールをインストールして実行し、Visual Studio からリモートコンピューターに接続するようにプロジェクトを構成してから、アプリをデプロイして実行します。

![リモートデバッガーコンポーネント](../debugger/media/remote-debugger-client-apps.png "Remote_debugger_components")

ユニバーサル Windows アプリ (UWP) のリモートデバッグの詳細については、「[インストールされているアプリパッケージのデバッグ](debug-installed-app-package.md)」を参照してください。

## <a name="requirements"></a>［要件］

リモートデバッガーは、windows 7 以降 (phone 以外) および windows server 2008 Service Pack 2 以降のバージョンでサポートされています。 要件の完全な一覧については、「[要件](../debugger/remote-debugging.md#requirements_msvsmon)」を参照してください。

> [!NOTE]
> プロキシ経由で接続されている2台のコンピューター間のデバッグはサポートされていません。 高待機時間接続または低帯域幅接続 (ダイヤルアップインターネットなど) またはインターネット経由でのデバッグは推奨されません。また、障害が発生する可能性があります。

## <a name="download-and-install-the-remote-tools"></a>リモート ツールのダウンロードおよびインストール

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> 場合によっては、ファイル共有からリモートデバッガーを実行する方が効率的な場合があります。 詳細については、「[ファイル共有からのリモートデバッガーの実行](../debugger/remote-debugging.md#fileshare_msvsmon)」を参照してください。

## <a name="BKMK_setup"></a> リモート デバッガーのセットアップ

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> 追加のユーザーにアクセス許可を追加する必要がある場合、リモートデバッガーの認証モードまたはポート番号を変更するには、「[リモートデバッガーの構成](../debugger/remote-debugging.md#configure_msvsmon)」を参照してください。

## <a name="remote_cplusplus"></a>プロジェクトのC++リモートデバッグ
 次の手順では、プロジェクトの名前とパスを C:\remotetemp\MyMfc にし、リモートコンピューターの名前を「 **Mjo-DL**」にします。

1. **mymfc** という名前の MFC アプリケーションを作成します。

2. ブレークポイントを、アプリケーション内の達しやすい任意の箇所 (たとえば、`CMainFrame::OnCreate` の開始時の **MainFrm.cpp**) に設定します。

3. ソリューションエクスプローラーで、プロジェクトを右クリックし、[**プロパティ**] を選択します。 **[デバッグ]** タブを開きます。

4. **[起動するデバッガー]** を **[リモート Windows デバッガー]** に設定します。

    ![Remoteデバッグ Cplus](../debugger/media/remotedebuggingcplus.png "RemoteDebuggingCPlus")

5. プロパティに次の変更を適用します。

   |設定|[値]|
   |-|-|
   |リモート コマンド|C:\remotetemp\mymfc.exe|
   |作業ディレクトリ|C:\remotetemp|
   |リモート サーバー名|MJO-DL:*ポート*番号|
   |Connection|Windows 認証を使用したリモート接続|
   |[デバッガーのタイプ]|ネイティブのみ|
   |[配置ディレクトリ]|C:\remotetemp|
   |[配置する追加ファイル]|C:\data\mymfcdata.txt|

    追加のファイルを展開する (オプション) 場合は、フォルダーが両方のコンピューターに存在している必要があります。

6. ソリューションエクスプローラーで、ソリューションを右クリックし、[ **Configuration Manager**] を選択します。

7. **[デバッグ]** 構成の **[配置]** チェック ボックスをオンにします。

    ![RemoteDebugCplusDeploy](../debugger/media/remotedebugcplusdeploy.png "RemoteDebugCplusDeploy")

8. デバッグを開始します (**[デバッグ] > [デバッグの開始]**、または **F5** キー)。

9. 実行可能ファイルが、リモート コンピューターに自動的に配置されます。

10. メッセージが表示されたら、リモートコンピューターに接続するためのネットワーク資格情報を入力します。

     必要な資格情報は、ネットワークのセキュリティ構成に固有のものです。 たとえば、ドメインコンピューターで、セキュリティ証明書を選択するか、ドメイン名とパスワードを入力することができます。 ドメイン以外のコンピューターでは、コンピューター名と有効なユーザーアカウント名 ( <strong>MJO-DL\name@something.com</strong>など) と、正しいパスワードを入力することができます。

11. Visual Studio コンピューターで、実行がブレークポイントで停止したことを確認できるはずです。

    > [!TIP]
    > また、これらのファイルは別の手順でも配置できます。 **ソリューション エクスプローラー**で、**[mymfc]** ノードを右クリックして **[配置]** を選択します。

    アプリケーションで必要な非コードファイルがある場合は、[**リモート Windows デバッガー** ] ページで**配置する追加ファイル**で指定できます。

    または、ファイルをプロジェクトに追加し、各ファイルの [**プロパティ**] ページで [**コンテンツ**] プロパティを **[はい]** に設定します。 これらのファイルは、[**リモート Windows デバッガー** ] ページで指定した**配置ディレクトリ**にコピーされます。 また、**配置ディレクトリ**のサブフォルダーにファイルをコピーする必要がある場合は、**項目の種類**を [**ファイルのコピー** ] に変更し、追加のプロパティを指定することもできます。

## <a name="set-up-debugging-with-remote-symbols"></a>リモート シンボルを使用したデバッグのセットアップ

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]

## <a name="see-also"></a>参照
- [Visual Studio でのデバッグ](../debugger/index.yml)
- [デバッガーでのはじめに](../debugger/debugger-feature-tour.md)
- [Windows ファイアウォールをリモート デバッグ用に構成する](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [リモート デバッガーのポートの割り当て](../debugger/remote-debugger-port-assignments.md)
- [リモートの IIS コンピューター上の ASP.NET のリモート デバッグ](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)
- [リモート デバッグ エラーとトラブルシューティング](../debugger/remote-debugging-errors-and-troubleshooting.md)
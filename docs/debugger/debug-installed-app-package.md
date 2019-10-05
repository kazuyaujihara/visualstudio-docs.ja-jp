---
title: インストールされている UWP アプリケーションパッケージをデバッグする |Microsoft Docs
ms.custom: ''
ms.date: 11/07/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.remote.connection
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- app package, debug
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: d5c2e94e9fa80145489bddfb005b7136bdff8a71
ms.sourcegitcommit: ea182703e922c74725045afc251bcebac305068a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71211292"
---
# <a name="debug-an-installed-uwp-app-package-in-visual-studio"></a>インストールされている UWP アプリパッケージを Visual Studio でデバッグする

Visual Studio では、Windows 10 コンピューターと Xbox、HoloLens、IoT デバイスでインストールされているユニバーサル Windows プラットフォーム (UWP) アプリパッケージをデバッグできます。

>[!NOTE]
>インストールされている UWP アプリの Visual Studio のデバッグは、電話ではサポートされていません。

UWP アプリのデバッグの詳細については、「[インストールされているアプリパッケージのデバッグ](https://devblogs.microsoft.com/devops/updates-for-debugging-installed-app-packages-in-visual-studio-2015-update-2/)」および「[ユニバーサル WINDOWS アプリ (UWP) のビルド](https://devblogs.microsoft.com/visualstudio/universal-windows-apps-targeting-windows-10-anniversary-sdk/)」のブログ記事を参照してください。

## <a name="debug-an-installed-uwp-app-on-a-local-machine"></a>ローカルコンピューターでインストールされている UWP アプリをデバッグする

1. Visual Studio で、[**デバッグ** > ] [**その他のデバッグターゲット** > ] **[インストールされているアプリケーションパッケージのデバッグ]** を選択します。

1. **[インストールされているアプリケーションパッケージのデバッグ]** ダイアログボックスの **[接続の種類]** で、 **[ローカルコンピューター]** を選択します。

1. **[インストールされたアプリパッケージ]** で、デバッグするアプリを選択するか、検索ボックスに名前を入力します。 実行されていないインストール済みのアプリパッケージは [実行されて**いません**] と表示され、実行中のアプリは**実行中です。**

   ![Debuginstalledapppackage](../debugger/media/debug-installed-app-pkg.png "Debuginstalledapppackage")

1. 必要に応じて、[**このコードの種類をデバッグ**する] でコードの種類を変更し、[その他のオプション] を選択します。
   - [**起動しないが、開始時にコードをデバッグ**する] を選択すると、アプリの起動時にデバッグが開始されます。 アプリが起動したときのデバッグを開始することは、カスタムパラメーターを使用したプロトコルアクティベーションなど、[さまざまな起動方法](/windows/uwp/xbox-apps/automate-launching-uwp-apps)から制御パスをデバッグするための効果的な方法です。

1. **[開始]** を選択するか、アプリが実行中の場合は **[アタッチ]** を選択します。

> [!NOTE]
> また、Visual Studio で [**デバッグ** > ] **[プロセスにアタッチ]** の順に選択して、実行中の UWP または他のアプリプロセスにアタッチすることもできます。 実行中のプロセスにアタッチするために元の Visual Studio プロジェクトは必要ありませんが、アプリのシンボルを読み込むことは、元のコードがないプロセスをデバッグする際に、大幅に役立ちます。 「[デバッガーでシンボルとソースファイルを指定する](specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)」を参照してください。

## <a name="remote"></a>リモートコンピューターまたはリモートデバイスでインストールされている UWP アプリをデバッグする

Visual Studio では、Windows 10 デバイスまたはリモートの作成者の更新プログラムの Windows 10 コンピューターにインストールされた UWP アプリを初めてデバッグするときに、ターゲットデバイスにリモートデバッグツールをインストールします。

1. Visual Studio コンピューターとリモートデバイスまたはコンピューターで[開発者モードを有効に](/windows/uwp/get-started/enable-your-device-for-development)します。

1. 作成前の Windows 10 を実行しているリモートコンピューターに接続している場合は、リモートコンピューターに[リモートデバッガーを手動でインストールして起動](../debugger/remote-debugging.md)します。

1. Visual Studio コンピューターで、[**他のデバッグターゲット** > をデバッグ] **[インストールされているアプリケーションパッケージのデバッグ]** **を選択し** > ます。

1. **[インストールされているアプリケーションパッケージのデバッグ]** ダイアログボックスの **[接続の種類]** で、 **[リモートコンピューター]** または **[デバイス]** を選択します。

   **[デバイス]** を選択した場合、コンピューターは Windows 10 デバイスに物理的に接続されている必要があります。

   リモートコンピューターの場合、 **[アドレス]** の横にコンピューターアドレスが表示されない場合は、 **[変更]** を選択します。

   1. **[リモート接続]** ダイアログボックスで、 **[アドレス]** の横に、接続先のコンピューターの名前または IP アドレスを入力します。

      ![ChooseRemoteComputer](../debugger/media/debug-remote-app-pkg.png "ChooseRemoteComputer")

      デバッガーがコンピューター名を使用してリモートコンピューターに接続できない場合は、代わりに IP アドレスを使用します。 Xbox、HoloLens、または IoT デバイスの IP アドレスを使用します。
   1. **[認証モード]** の横にある認証オプションを選択します。

      ほとんどのアプリでは、既定値の [ **Universal (暗号化**されていないプロトコル)] をそのまま使用します。
   1. **[選択]** を選択します。

1. **[インストールされたアプリパッケージ]** で、デバッグするアプリを選択するか、検索ボックスに名前を入力します。 実行されていないインストール済みのアプリパッケージは [実行されて**いません**] と表示され、実行中のアプリは**実行中です。**

1. 必要に応じて、[**このコードの種類をデバッグ**する] でコードの種類を変更し、[その他のオプション] を選択します。
   - [**起動しないが、開始時にコードをデバッグ**する] を選択すると、アプリの起動時にデバッグが開始されます。 アプリが起動したときのデバッグを開始することは、カスタムパラメーターを使用したプロトコルアクティベーションなど、[さまざまな起動方法](/windows/uwp/xbox-apps/automate-launching-uwp-apps)から制御パスをデバッグするための効果的な方法です。

1. **[開始]** を選択するか、アプリが実行中の場合は **[アタッチ]** を選択します。

接続されている Xbox、HoloLens、または IoT デバイスにインストールされているアプリパッケージのデバッグを初めて開始すると、Visual Studio によってターゲットデバイスの正しいバージョンのリモートデバッガーがインストールされます。 リモートデバッガーのインストールには時間がかかる場合があり、**リモートデバッガーの起動**中にメッセージが表示されます。

>[!NOTE]
>現在、Xbox または HoloLens デバイスが既に実行されている場合は、デバッガーがアタッチされた状態でアプリが再起動されます。

UWP アプリのリモート展開の詳細については、「[リモートコンピューターで](run-windows-store-apps-on-a-remote-machine.md)の[Uwp アプリのデプロイとデバッグ](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)」と「uwp アプリのデバッグ」を参照してください。

## <a name="see-also"></a>関連項目

- [Visual Studio でのデバッグ](../debugger/index.yml)
- [デバッガーでのはじめに](../debugger/debugger-feature-tour.md)
- [リモート デバッグ](../debugger/remote-debugging.md)
- [Windows ファイアウォールをリモート デバッグ用に構成する](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [リモート デバッガーのポートの割り当て](../debugger/remote-debugger-port-assignments.md)
- [リモート デバッグ エラーとトラブルシューティング](../debugger/remote-debugging-errors-and-troubleshooting.md)
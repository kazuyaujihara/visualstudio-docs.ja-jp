---
title: UWP アプリのデバッグセッションを開始する |Microsoft Docs
ms.custom: seodec18
ms.date: 11/20/2018
ms.topic: conceptual
f1_keywords:
- VC.Project.IVCAppHostRemoteDebugPageObject.MachineName
- VC.Project.IVCAppHostRemoteDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostTetheredDebugPageObject.DebuggerType
- VC.Project.IVCAppHostLocalDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostRemoteDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.DebuggerType
- ImmersiveProjects.Properties.Debug
- VC.Project.IVCAppHostTetheredDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostLocalDebugPageObject.AllowLocalNetworkLoopback
- AppPackage.Properties.Debug
- VC.Project.IVCAppHostRemoteDebugPageObject.Authentication
- VC.Project.IVCAppHostRemoteDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.BreakpointBehavior
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: c4504dda362c8a50f33168a12839e894a14316d7
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72436007"
---
# <a name="start-a-debugging-session-for-a-uwp-app"></a>UWP アプリのデバッグ セッションを開始する

この記事では、ユニバーサル Windows プラットフォーム (UWP) アプリの Visual Studio デバッグセッションを開始する方法について説明します。 UWP アプリはC++、xaml、xaml、およびC#Visual Basic で記述できます。 UWP アプリのデバッグを開始するには、デバッグセッションを構成し、アプリを起動する方法を選択します。

::: moniker range=">=vs-2019"
> [!NOTE]
> Visual Studio 2019 以降では、HTML および JavaScript 用の UWP アプリはサポートされなくなりました。
::: moniker-end
::: moniker range="vs-2017"
Visual Studio 2017 では、この記事に示されているほとんどのコマンドとオプションは、HTML および JavaScript の UWP アプリにも適用されます。 コマンドが管理対象アプリとC++アプリ間で異なる場合、JavaScript アプリは通常、UWP C++アプリのコマンドと同じです。
::: moniker-end

## <a name="BKMK_The_easy_way_to_start_debugging"></a>Visual Studio ツールバーからデバッグを開始する

デバッグを構成して開始する最も簡単な方法は、標準の Visual Studio ツールバーを利用することです。

![ツールバーからのデバッグ](../debugger/media/vsrun_select_target_device.png)

1. **[標準]** ツールバーの **[構成]** ドロップダウンで、 **[デバッグ]** を選択します。

1. **[プラットフォーム]** ドロップダウンから、ビルドするターゲットプラットフォームを選択します。

1. 緑色の矢印の横にあるドロップダウンから、デバッグターゲットを選択します。 ローカルコンピューター、直接接続されているデバイス、ローカルの Visual Studio シミュレーター、リモートデバイス、またはエミュレーターを選択できます。

1. デバッグを開始するには、ツールバーの緑色の**開始**矢印を選択するか、 **[デバッグ]**  >  **[デバッグ開始]** を選択するか、 **F5**キーを押します。

   Visual Studio によってアプリがビルドされ、アタッチされたデバッガーが起動します。

デバッグは、ブレークポイントに達するか、実行が手動で中断されるか、ハンドルされない例外が発生するか、アプリが終了するまで続行されます。

### <a name="BKMK_Choose_the_deployment_target"></a>配置ターゲットのオプション

デバッグターゲットは、Visual Studio のツールバーまたはプロジェクトのデバッグプロパティページで設定できます。 次のいずれかのオプションを選択します。

|||
|-|-|
|**ローカル コンピューター**|ローカル コンピューターの現在のセッションでアプリをデバッグします。|
|**シミュレーター**|UWP アプリ用の Visual Studio シミュレーターでアプリをデバッグします。 シミュレーターは、ローカルコンピューターに存在しない可能性があるタッチジェスチャやデバイスのローテーションなどのデバイス機能をシミュレートするデスクトップウィンドウです。 シミュレーターオプションは、アプリの**ターゲットプラットフォームの最小バージョン**がローカルコンピューターのオペレーティングシステム以下である場合にのみ使用できます。 詳細については、「[シミュレーターで UWP アプリを実行する](../debugger/run-windows-store-apps-in-the-simulator.md)」を参照してください。|
|**リモート コンピューター**|ネットワークまたはイーサネットケーブル経由でローカルコンピューターに接続されているデバイスでアプリをデバッグします。 Remote Tools for Visual Studio がリモートデバイスにインストールされ、実行されている必要があります。 詳細については、「[リモートコンピューターでの UWP アプリの実行](../debugger/run-windows-store-apps-on-a-remote-machine.md)」を参照してください。|
|**デバイス**|USB 接続デバイスでアプリをデバッグします。 デバイスは、開発者がロックを解除し、画面のロックを解除する必要があります。|
|**モバイルエミュレーター**|エミュレーター名で指定されたエミュレーターを起動し、アプリをデプロイして、デバッグを開始します。 エミュレーターは、Hyper-v が有効になっているコンピューターでのみ使用できます。|

## <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a>プロジェクトのプロパティページでデバッグを構成する

追加のデバッグオプションを構成するには、プロジェクトの [デバッグ] プロパティページを使用します。

**デバッグプロパティを開くには、次のようにします。**

1. **ソリューションエクスプローラー**でプロジェクトを選択し、 **[プロパティ]** アイコンを選択するか、プロジェクトを右クリックして **[プロパティ]** を選択します。

1. **[プロパティ]** ペインの左側で、次のようにします。

   - アプリC#と Visual Basic アプリの場合は、 **[デバッグ]** を選択します。

     ![C#および Visual Basic プロジェクトデバッグ プロパティページ](../debugger/media/dbg_csvb_debugpropertypage.png)

   - アプリC++の場合は、 **[構成プロパティ]**  >  **[デバッグ]** を選択します。

     ![C++UWP アプリのデバッグプロパティページ](../debugger/media/dbg_cpp_debugpropertypage.png)

### <a name="BKMK_Choose_the_debugger_to_use"></a> 使用するデバッガーを選択する

アプリC#と Visual Basic アプリの場合、Visual Studio は既定でマネージコードをデバッグします。 他のコード型または追加のコードの種類をデバッグすることを選択できます。 また、プロジェクトの一部であるバックグラウンドタスクについて、**デバッガーの種類**の値を設定することもできます。

アプリC++では、Visual Studio は既定でネイティブコードをデバッグします。 ネイティブコードの代わりに、またはネイティブコードに加えて、特定の種類のコードをデバッグすることを選択できます。

**デバッグするコードの種類を指定するには:**

- アプリC#と Visual Basic アプリの場合は、 **[デバッグ]** プロパティページの **[デバッガー]** の種類 の下にある **[アプリケーション]** の種類 と **[バックグラウンドプロセスの種類]** ドロップダウンから、次のいずれかのデバッガーを選択します。

- アプリC++の場合、 **[デバッグ]** プロパティページの **[デバッガーの種類]** ドロップダウンから、次のいずれかのデバッガーを選択します。

|||
|-|-|
|**マネージドのみ**|アプリのマネージド コードをデバッグします。 JavaScript コードとネイティブ C/C++ コードは無視されます。|
|**ネイティブのみ**|アプリのネイティブ コードと C/C++ コードをデバッグします。 マネージド コードと JavaScript コードは無視されます。|
|**混合 (マネージドとネイティブ)**|アプリのネイティブ C/C++ コードとマネージド コードをデバッグします。 JavaScript コードは無視されます。 プロジェクトC++では、このオプションは "**マネージ" と "ネイティブ**" と呼ばれます。|
|**スクリプト**|アプリの JavaScript コードをデバッグします。 マネージド コードとネイティブ コードは無視されます。|
|**スクリプトを利用したネイティブ コード**|アプリでネイティブ CC++ /コードおよび JavaScript コードをデバッグします。 マネージコードは無視されます。 プロジェクトまたC++はバックグラウンドタスクでのみ使用できます。|
|**GPU のみ (C++ AMP)**|GPU (Graphics Processing Unit) で実行されるネイティブ C++ コードをデバッグします。 プロジェクトでC++のみ使用できます。|

### <a name="BKMK__Optional__Disable_network_loopbacks"></a>Network ループバックをを無効にする (省略可能)

 セキュリティのために、標準の方法でインストールされた UWP アプリは、インストールされているデバイスに対してネットワーク呼び出しを行うことはできません。 Visual Studio 除外さは、既定でこの規則からアプリを展開するため、1台のコンピューターで通信手順をテストできます。 アプリをリリースする前に、除外を行わずにアプリをテストする必要があります。

**ネットワーク ループバックの免除を削除するには:**

- アプリC#と Visual Basic アプリの場合は、 **[デバッグ]** プロパティページの **[開始オプション]** の下にある **[ローカルネットワークループバックを許可する]** チェックボックスをオフにします。

- アプリC++の場合は、 **[デバッグ]** プロパティページの **[ローカルネットワークループバックを許可する]** ドロップダウンから **[いいえ]** を選択します。

### <a name="BKMK__Optional__Reinstall_the_app_when_you_start_debugging"></a>デバッグを開始するときにアプリを再インストールする (省略可能)
 または Visual Basic アプリでインストールの問題を診断するには、 **[デバッグ]** プロパティページで アンインストール を選択し、 **[パッケージの再インストール]** をクリックします。 C# このオプションは、デバッグの開始時に元のインストールを再作成します。 このオプションはプロジェクトでC++は使用できません。

### <a name="BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger"></a>リモートデバッグの認証オプションを設定する

既定では、リモートデバッガーを実行するために、配置ターゲットとして **[リモートコンピューター]** を選択したときに、Windows 資格情報を指定する必要があります。 認証要件を変更できます。

**ユニバーサル (暗号化**されていないプロトコル) 認証モードは、IoT、Xbox、HoloLens デバイス、および作成者の更新プログラムまたはそれ以降の Windows 10 pc を対象としています。

**認証方法を変更するには:**

- アプリC#と Visual Basic アプリの場合は、 **[デバッグ]** プロパティページで、**ターゲットデバイス**として **[リモートコンピューター]** を選択します。 次に、**認証モード**として [なし] または [**ユニバーサル (暗号化**されてい**ない**プロトコル)] を選択します。

- アプリC++の場合は、 **[デバッグ]** プロパティページで [**デバッガーを起動する** **リモートコンピューター** ] を選択します。 次に、**認証の種類**として **[認証なし]** または **[ユニバーサル (暗号化]** されていないプロトコル) を選択します。

> [!CAUTION]
> リモートデバッガーを**None**または**Universal (暗号化**されていないプロトコル) モードで実行した場合、ネットワークセキュリティはありません。 悪意のあるコードや悪意のあるトラフィックから危険にさらされていないことが確実である信頼されたネットワークでのみ、これらのモードを選択してください。

## <a name="BKMK_Start_the_debugging_session"></a>デバッグの開始オプション

[@No__t_1**デバッグ**] を選択して**デバッグを開始**するか、 **F5**キーを押すと、Visual Studio によってデバッガーがアタッチされた状態でアプリが起動されます。 実行は、ブレークポイントに達するか、実行が手動で中断されるか、ハンドルされない例外が発生するか、アプリが終了するまで続行されます。

### <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a>デバッグを開始しますが、アプリの開始を遅らせます

既定では、Visual Studio は、デバッグを開始するとすぐにアプリを起動します。 また、デバッグモードで実行するようにアプリを設定することもできますが、デバッガーの外部でアプリを起動することもできます。 たとえば、Windows の **[スタート]** メニューからアプリの起動をデバッグしたり、アプリでバックグラウンドプロセスをデバッグしたりすることができます。 このオプションを選択した場合、アプリは起動時にデバッガーで開始されます。

**アプリの自動起動を無効にするには:**

- およびC# Visual Basic アプリの場合は、 **[デバッグ]** プロパティページの **[開始オプション]** で 起動し **[ないが、コードをデバッグする]** を選択します。

- アプリC++の場合は、 **[デバッグ]** プロパティページの **[アプリケーションの起動]** ドロップダウンから **[いいえ]** を選択します。

バックグラウンドタスクのデバッグの詳細については、「 [UWP アプリの中断イベント、再開イベント、およびバックグラウンドイベントのトリガー](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)」を参照してください。

### <a name="BKMK_Start_an_installed_app_in_the_debugger"></a>インストールされている、または実行中の UWP アプリをデバッグする

インストール済みの**アプリケーションパッケージのデバッグ**を使用して、ローカルまたはリモートデバイスで既にインストールまたは実行されている UWP アプリをデバッグすることができます。 アプリが Microsoft Store からインストールされているか、Visual Studio プロジェクトではない可能性があります。 たとえば、Visual Studio を使用しないカスタムビルドシステムがアプリに含まれている可能性があります。

インストールされているアプリをすぐに起動することも、別の方法で起動したときにデバッガーで実行するように設定することもできます。 詳細については、「 [UWP アプリの中断、再開、およびバックグラウンドイベントのトリガー](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)」を参照してください。

インストールされている、または実行**中の UWP**アプリをデバッガーで開始するには、[デバッグ] [**インストールされているアプリケーションパッケージ** >  デバッグする **] を選択**し  >  ます。 詳細については、「[インストールされているアプリパッケージのデバッグ](../debugger/debug-installed-app-package.md)」を参照してください。

### <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a>実行中の Windows 8.x アプリにデバッガーをアタッチする

[!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] アプリにデバッガーをアタッチするには、デバッグ可能パッケージ マネージャーを使用して、デバッグ モードで実行するようにアプリを設定する必要があります。 デバッグ可能パッケージマネージャーは、Remote Tools for Visual Studio と共にインストールされます。

1. アプリがインストールされているデバイスに Remote Tools for Visual Studio をインストールします。 詳細については、「[リモートツールのインストール](../debugger/remote-debugging.md)」を参照してください。

1. Windows の**スタート**画面で、デバッグ可能な**パッケージマネージャー**を検索して開始します。

   AppxDebug コマンドレット用に適切に構成された PowerShell ウィンドウが表示されます。

1. アプリの PackageFullName 識別子を指定します。

   1. すべてのアプリの PackageFullName を含む一覧を表示するには、PowerShell プロンプトで「`Get-AppxPackage`」と入力します。

   1. PowerShell プロンプトで、`Enable-AppxDebug <PackageFullName>` を入力します。ここで \<PackageFullName > はアプリの PackageFullName 識別子です。

1. **[デバッグ]**  >  **[プロセスにアタッチ]** の順に選択します。

1. **[プロセスにアタッチ]** ダイアログボックスで、 **[接続先]** ボックスにリモートデバイスを指定します。

   デバイス名を入力するか、 **[接続先]** ボックスのドロップダウンから選択するか、 **[検索]** を選択して **[リモート接続]** ダイアログボックスでデバイスを検索することができます。

1. デバッグするコードの種類を指定するには、 **[アタッチ先]** ボックスの横にある **[選択]** を選択します。

1. **[コードの種類の選択**] ダイアログボックスで、次のいずれかを選択します。
   - **デバッグするコードの種類を自動的に決定**します。
   - **これらのコードの種類をデバッグ**し、一覧から1つまたは複数のコードの種類を選択します。

1. [選択**可能なプロセス**] ボックスの一覧で、デバッグするアプリプロセスを選択します。

1. **[アタッチ]** を選択します。

 Visual Studio によって、デバッガーがプロセスにアタッチされます。 実行は、ブレークポイントに達するか、実行が手動で中断されるか、ハンドルされない例外が発生するか、アプリが終了するまで続行されます。

::: moniker range="vs-2017"
> [!NOTE]
> JavaScript アプリは、*wwahost.exe* プロセスのインスタンスで実行されます。 複数の JavaScript アプリが実行されている場合は、アプリの*wwahost .exe*プロセスの数値プロセス ID (PID) を把握しておく必要があります。
>
> JavaScript アプリにアタッチする最も簡単な方法は、他のすべての JavaScript アプリを閉じることです。 または、アプリを起動する前に、Windows タスクマネージャーで実行中の*wwahost*のプロセスの pid をメモすることができます。 アプリを起動すると、それまでにメモしたものとは異なる*wwahost .Exe* PID が使用されます。
::: moniker-end

## <a name="see-also"></a>関連項目

- [Visual Studio でのアプリのデバッグ](../debugger/debugging-windows-store-and-windows-universal-apps.md)
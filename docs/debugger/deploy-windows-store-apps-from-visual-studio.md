---
title: UWP アプリをデプロイする |Microsoft Docs
ms.custom: seodec18
ms.date: 01/16/2018
ms.topic: conceptual
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
ms.openlocfilehash: b2fa0bd62b88602ee5a4d5091821e2c2a18f6374
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72430765"
---
# <a name="deploy-uwp-apps-from-visual-studio"></a>Visual Studio から UWP アプリを展開する

Visual Studio の配置機能では、Visual Studio で作成された UWP アプリをターゲットデバイスにビルドして登録します。 アプリの厳密な登録方法は、ターゲット デバイスがローカルかリモートかによって違います。

- ターゲットがローカルの Visual Studio コンピューターの場合、Visual Studio はアプリをビルド フォルダーから登録します。

- ターゲットがリモート デバイスの場合、Visual Studio は必要なファイルをリモート コンピューターにコピーしてから、そのデバイス上でアプリを登録します。

**[デバッグの開始]** オプション (キーボード: F5) または **[デバッグなしで開始]** オプション (キーボード: CTRL + F5) を使用して Visual Studio からアプリをデバッグする場合、展開は自動的に行われます。 アプリを手動で配置することも可能です。 次のシナリオでは、手動の配置は有効です。

- ローカル コンピューターまたはリモート コンピューターで行う臨時のテスト。

- デバッグ対象のアプリを起動するためのアプリを配置する場合。

- 別のアプリまたはメソッドによって起動される、デバッグ対象のアプリを配置します。

## <a name="BKMK_How_to_deploy_a_Windows_Store_app"></a>UWP アプリをデプロイする方法
 アプリを手動で配置する手順はシンプルです。

1. リモート デバイスへ配置する場合は、アプリのスタートアップ プロジェクトのプロパティ プロジェクト ページに、デバイスの名前または IP アドレスを指定します。 (指定するステップはこのトピック内で後述)。

2. デバッガーの Visual Studio ツールバーで、 **[デバッグの開始]** ボタンの横のドロップダウン リストから配置ターゲットを選択します。

     ![ローカルコンピューターで実行する](../debugger/media/vsrun_f5_local.png "VSRUN_F5_Local")

3. **[ビルド]** メニューで **[配置]** を選択

## <a name="BKMK_How_to_specify_a_remote_device"></a> リモート デバイスの指定方法

**必須コンポーネント**

Windows 10 のリモート デバイスで有効にする必要があります[開発者モード](/windows/uwp/get-started/enable-your-device-for-development)します。 Creator の更新プログラムを実行する Windows 10 デバイスで以降、リモート ツールが自動的にインストールされているアプリを展開するときにします。 詳細については、次を参照してください。 [インストールされているアプリ パッケージをデバッグ](../debugger/debug-installed-app-package.md)します。

> [!NOTE]
> Windows 10 の作成前の更新プログラムのバージョンでは、リモートデバイスに Remote Tools for Visual Studio がインストールされており、リモートデバッガーが実行されている必要があります。

配置では、リモート デバッガーのネットワーク チャネルを使用して、アプリのファイルをリモート デバイスに送信します。

#### <a name="to-specify-a-remote-device"></a>リモート デバイスを指定するには

1. スタートアップ プロジェクトのデバッグ プロパティ ページで、リモートの配置ターゲットの名前または IP アドレスを指定します。

2. デバッグ プロパティ ページを開くには、ソリューション エクスプローラーでプロジェクトを選択してから、ショートカット メニューで **[プロパティ]** を選択します。

3. 次に、プロパティ ページ ウィンドウで **[デバッグ]** ノードを選択します。

4. **[ターゲットデバイス]** で、 **[リモートコンピューター]** を選択します。

5. **[リモートコンピューター]** の **[検索]** をクリックします。

6. リモートデバイスの名前または IP アドレスを入力するか、 **[リモート接続]** ダイアログボックスからデバイスを選択することができます。

    ![[リモートデバッガー接続の選択] ダイアログボックス](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")

    **[リモート接続]** ダイアログボックスには、ローカルネットワークサブネット上のデバイス、およびイーサネットケーブルによって Visual Studio コンピューターに直接接続されているデバイスが表示されます。

   **C++プロジェクトページでのリモートデバイスの指定**

   ![リモート&#43; &#43;デバッグのための C プロジェクトプロパティ](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")

7. **[起動するデバッガー]** ボックスの一覧の **[リモート デバッガー]** をクリックします。

8. **[コンピューター名]** ボックスのリモート デバイスにネットワーク名を入力します。 あるいはボックス内の下向き矢印をクリックして、[リモート デバッガー接続の選択] ダイアログ ボックスからデバイスを選択します。

   **Visual C# および Visual Basic のプロジェクト ページにあるリモート デバイスを指定**

   ![リモートデバッグのマネージプロジェクトのプロパティ](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")

9. **[ターゲット デバイス]** ボックスの一覧の **[リモート コンピューター]** をクリックします。

10. リモート デバイスのネットワーク名を **[リモート コンピューター]** ボックスに入力するか、 **[検索]** をクリックし、 **[リモート デバッガー接続の選択]** ダイアログ ボックスでデバイスを選択します。

## <a name="BKMK_Deployment_options"></a> 配置オプション

次の配置オプションを、スタートアップ プロジェクトのデバッグ プロパティ ページに設定できます。

**ネットワーク ループバックの許可**

セキュリティ上の理由から、標準の方法でインストールされた UWP アプリまたは [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] アプリは、インストール先のデバイスに対してネットワーク呼び出しを行うことはできません。 既定では、Visual Studio による配置では、配置されたアプリに対するこの規則の適用は免除されます。 この免除によって、1 台のコンピューター上で通信プロシージャをテストできます。 アプリを [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]に送信する前に、アプリを適用除外せずにテストする必要があります。

アプリからネットワーク ループバックの適用除外を削除するには

- C#および Visual Basic デバッグ プロパティページで、**ネットワークループバックを許可する** チェックボックスをオフにします。

- C++デバッグ] プロパティページで、[ **[ネットワークループバックの許可]** の値を **[いいえ]** に設定します。

**起動しないが、開始時にコードC#をデバッグする (および Visual Basic)/アプリケーションをC++起動する ()**

アプリが起動した場合はデバッグ セッションを自動駅に開始するように、配置を構成するには

- C#および Visual Basic デバッグ] プロパティページで、[ **[起動しないが、開始時にコードをデバッグする]** チェックボックスをオンにします。

- C++デバッグ] プロパティページで、[ **[アプリケーションの起動]** の値を **[はい]** に設定します。

## <a name="see-also"></a>参照

- [高度なリモート配置オプション](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)
- [インストールされているアプリケーション パッケージをデバッグする](../debugger/debug-installed-app-package.md)
- [Visual Studio からアプリを実行](/visualstudio/debugger/debugging-windows-store-and-windows-universal-apps)

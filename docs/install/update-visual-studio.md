---
title: Visual Studio 2017 を更新する
titleSuffix: ''
description: Visual Studio を最新のリリースに更新する詳細な手順を説明します。
ms.date: 03/21/2019
ms.custom: seodec18
ms.topic: conceptual
ms.prod: visual-studio-windows
ms.technology: vs-installation
helpviewer_keywords:
- update [Visual Studio]
- change [Visual Studio]
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 945250660e80353ea536986e5149f8814d1fe563
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58323595"
---
# <a name="update-visual-studio-to-the-most-recent-release"></a>Visual Studio を最新リリースに更新する

::: moniker range="vs-2017"

常に最新の機能、修正、改善を利用できるように、Visual Studio 2017 の[最新バージョン](/visualstudio/releasenotes/vs2017-relnotes/)に更新することをお勧めします。

さらに、次のバージョンを試したい場合は、Visual Studio 2019 の[リリース候補](//visualstudio/releases/2019/release-notes/)のダウンロードも検討してください。

> [!IMPORTANT]
> Visual Studio をインストール、更新、または変更するには、管理アクセス許可を持つアカウントでログオンする必要があります。 詳細については、「[ユーザー アクセス許可と Visual Studio](../ide/user-permissions-and-visual-studio.md)」を参照してください。
>
> [!NOTE]
> このトピックは、Windows 上の Visual Studio に適用されます。 Visual Studio for Mac については、「[Visual Studio for Mac を更新する](/visualstudio/mac/update)」を参照してください。

## <a name="update-visual-studio-2017-version-156-or-later"></a>Visual Studio 2017 バージョン 15.6 以降を更新する

IDE 内から直接使用しやすくするために、インストールと更新プログラムのエクスペリエンスが整理されました。 ここでは、バージョン 15.6 以降から新しいバージョンの Visual Studio に更新する方法について説明します。

### <a name="use-the-notifications-hub"></a>通知ハブを使用する

更新プログラムがある場合、Visual Studio には対応する通知フラグが表示されます。

1. 作業内容を保存します。

1. 通知フラグを選択して**通知**ハブを開き、インストールする更新プログラムを選択します。

   ![通知ハブを使用して Visual Studio 2017 を更新する](media/vs-install-notifications-hub-15dot6.png "Visual Studio 2017 の 通知ハブ")

1. **[更新]** ダイアログ ボックスが開いたら、**[今すぐ更新]** を選択します。

    ![通知ハブから [更新] ダイアログ ボックスを使用して Visual Studio 2017 を更新する](media/vs-update-now-from-notifications-hub.png "Visual Studio の通知ハブの [更新] ダイアログ ボックス")

     [ユーザー アクセス制御] ダイアログ ボックスが開いたら、**[はい]** を選択します。 [お待ちください] ダイアログが表示されることがあります。処理が完了すると、Visual Studio インストーラーが開き、更新が開始されます。

     ![バージョン 15.6 の Visual Studio インストーラーの新しいエクスペリエンス](media/visual-studio-15dot6-installer.png "バージョン 15.6 の Visual Studio インストーラーの新しいエクスペリエンス")

     更新が続行されます。 処理が完了すると、Visual Studio が再起動されます。

     > [!NOTE]
     > Visual Studio を管理者モードで実行する場合は、更新後に Visual Studio を手動で再起動する必要があります。

### <a name="use-the-ide"></a>IDE を使用する

更新プログラムを確認し、Visual Studio のメニュー バーから更新プログラムをインストールすることができます。

1. 作業内容を保存します。

1. **[ヘルプ]** > **[更新プログラムの確認]** を選択します。

     ![Visual Studio バージョン 15.6 の新しい [ヘルプ] メニュー](media/vs-help-menu-check-for-updates.png "Visual Studio バージョン 15.6 の新しい [ヘルプ] メニュー")

1. **[更新]** ダイアログ ボックスが開いたら、**[今すぐ更新]** を選択します。

   前のセクションと同様に更新が実行され、更新が正常に完了すると Visual Studio が再起動されます。

   > [!NOTE]
   > Visual Studio を管理者モードで実行する場合は、更新後に Visual Studio を手動で再起動する必要があります。

### <a name="use-the-visual-studio-installer"></a>Visual Studio インストーラーを使用する

Visual Studio の以前のバージョンと同様に、Visual Studio インストーラーを使用して更新プログラムをインストールすることもできます。

1. 作業内容を保存します。

1. インストーラーを開きます。 必要に応じて、Visual Studio インストーラーを更新してから続行します。

   > [!NOTE]
   > Windows 10 を実行しているコンピューターの場合、**V** という文字の下に **Visual Studio インストーラー**と表示されるか、**M** という文字の下に **Microsoft Visual Studio インストーラー**と表示されます。

1. インストーラーの **[製品]** ページで、インストールされている Visual Studio のエディションを探します。

1. 更新プログラムが使用可能な場合は、**[更新]** ボタンが表示されます  (使用可能な更新プログラムがあるかどうかをインストーラーが判断するために数秒かかる場合があります)。

   **[更新]** ボタンを選択して更新プログラムをインストールします。

     ![Visual Studio インストーラーを使用して Visual Studio 2017 を更新する](media/update-visual-studio.png "Visual Studio インストーラーを使用して Visual Studio 2017 を更新する")

## <a name="update-visual-studio-2017-version-155-or-earlier"></a>Visual Studio 2017 バージョン 15.5 以前のバージョンを更新する

以前のバージョンを使用している場合、Visual Studio 2017 バージョン 15.0 からバージョン 15.5 の更新プログラムを適用するには、次の手順を実行します。

### <a name="update-by-using-the-notifications-hub"></a>通知ハブを使用して更新する

1. 更新プログラムがある場合、Visual Studio には対応する通知フラグが表示されます。

   ![通知ハブを使用して Visual Studio 2017 を更新する](media/notification-flag.png "Visual Studio の更新プログラムがあることを知らせる通知フラグ")

   通知フラグを選択して、**通知**ハブを開きます。

   ![通知ハブを使用して Visual Studio 2017 を更新する](media/notifications-hub.png "Visual Studio の通知ハブ")

1. **["Visual Studio 更新プログラム" が使用可能です]** を選択すると、**[拡張機能と更新プログラム]** ダイアログ ボックスが開きます。

   ![通知ハブを使用して Visual Studio 2017 を更新する](media/notifications-hub-select.png "Visual Studio の通知ハブ")

1. **[拡張機能と更新プログラム]** ダイアログ ボックスで、**[更新]** ボタンを選択します。

   ![通知ハブを使用して Visual Studio 2017 を更新する](media/notifications-extensions-and-updates.png "Visual Studio の [拡張機能と更新プログラム] ダイアログ")

#### <a name="more-about-visual-studio-notifications"></a>Visual Studio の通知の詳細

Visual Studio は、Visual Studio 自体またはいずれかのコンポーネントの更新プログラムが入手可能な場合に通知します。また、Visual Studio 環境で特定のイベントが発生した場合も通知します。

* 通知フラグが黄色の場合は、インストールできる Visual Studio 製品の更新プログラムが存在します。
* 通知フラグが赤の場合は、ライセンスに問題があります。
* 通知フラグが黒の場合は、確認のためのオプション メッセージまたは情報メッセージが存在します。

通知フラグを選択して**通知**ハブを開いてから、操作する通知を選択します。 または、通知を無視するか破棄するかを選択します。

 ![通知ハブでオプション メッセージまたは情報メッセージを表示する](media/notification-flag-optional.png "Visual Studio のオプション メッセージまたは情報メッセージの通知フラグ")

通知を無視することを選択した場合は、Visual Studio で表示されなくなります。 無視される通知のリストをリセットする場合は、通知ハブの **[設定]** ボタンを選択します。

   ![通知オプションを表示するために通知ハブの [設定] ボタンを選択する](media/vs-notifications-hub-settings-button.png "通知オプションを表示するために通知ハブの [設定] ボタンを選択する")

### <a name="update-by-using-the-visual-studio-installer"></a>Visual Studio インストーラーを使用して更新する

1. インストーラーを開きます。 続行する前に、インストーラーの更新が必要な場合があります。 更新が必要な場合は、更新するよう求められます。

   > [!NOTE]
   > Windows 10 を実行しているコンピューターの場合、**V** という文字の下に **Visual Studio インストーラー**と表示されるか、**M** という文字の下に **Microsoft Visual Studio インストーラー**と表示されます。

1. インストーラーの **[製品]** ページで、インストールされている Visual Studio のエディションを探します。

1. 更新プログラムが使用可能な場合は、**[更新]** ボタンが表示されます  (使用可能な更新プログラムがあるかどうかをインストーラーが判断するために数秒かかる場合があります)。

   **[更新]** ボタンを選択して更新プログラムをインストールします。

     ![Visual Studio インストーラーを使用して Visual Studio 2017 を更新する](media/update-visual-studio.png "Visual Studio インストーラーを使用して Visual Studio を更新する")

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>関連項目

* [Visual Studio の変更](modify-visual-studio.md)
* [Visual Studio のアンインストール](uninstall-visual-studio.md)
* [Visual Studio for Mac の更新](/visualstudio/mac/update)

::: moniker-end

::: moniker range="vs-2019"

常に最新の機能、修正、改善を利用できるように、Visual Studio 2019 の[最新バージョン](/visualstudio/releases/2019/release-notes/)に更新することをお勧めします。

> [!IMPORTANT]
> Visual Studio をインストール、更新、または変更するには、管理アクセス許可を持つアカウントでログオンする必要があります。 詳細については、「[ユーザー アクセス許可と Visual Studio](../ide/user-permissions-and-visual-studio.md)」を参照してください。
>
> [!NOTE]
> このトピックは、Windows 上の Visual Studio に適用されます。 Visual Studio for Mac については、「[Visual Studio for Mac を更新する](/visualstudio/mac/update)」を参照してください。

ここでは、Visual&nbsp;Studio&nbsp;2019&nbsp;Preview または Visual&nbsp;Studio&nbsp;2019&nbsp;RC を更新する方法について説明します。

## <a name="use-the-visual-studio-installer"></a>Visual Studio インストーラーを使用する

1. インストーラーを開きます。

     ![Visual Studio インストーラーを開く](media/vs2019-visual-studio-installer.png "Visual Studio インストーラーを開く")

   続行する前に、インストーラーの更新が必要な場合があります。 その場合は、画面の指示に従います。

1. インストーラーで、インストールした Visual Studio のエディションを探します。

   たとえば、以前にインストールした Visual &nbsp;Studio Community&nbsp;2019&nbsp;RC に対して更新プログラムが存在する場合は、**更新プログラム提供中**というメッセージが表示されます。

     ![更新する Visual Studio 2019 のエディションを選択する](media/vs2019-update-visual-studio-community-rc.png "更新する Visual Studio 2019 のエディションを選択する")

1. **[更新]** を選択して更新プログラムをインストールします。

    ![[更新] ボタンを選択して更新プログラムをインストールする](media/vs2019-choose-update-visual-studio-community-rc.png "[更新] ボタンを選択して更新プログラムをインストールする")

1. 更新が完了したら、**[起動]** を選択して Visual Studio を起動します。

    ![[起動] ボタンを選択して Visual Studio を起動する](media/vs2019-choose-launch-visual-studio-community-rc.png "[起動] ボタンを選択して Visual Studio を起動する")

## <a name="use-the-ide"></a>IDE を使用する

1. Visual Studio を開きます。 
 
    ![Visual Studio 2019 RC を開く](media/vs2019-visual-studio-rc.png "Windows から Visual Studio 2019 を開く")

1. **[作業の開始]** で、任意のオプションを選択すると、IDE が開きます。

    ![Visual Studio インストーラーを開く](media/vs2019-choose-option-from-get-started.png "Visual Studio インストーラーを開く")

    Visual Studio が開きます。 IDE 内に、**Visual Studio 2019 の更新プログラム**に関するメッセージが表示されます。

    ![IDE 内の Visual Studio 2019 の更新プログラムに関するメッセージ](media/vs2019-update-visual-studio-ide-message.png "IDE 内の Visual Studio 2019 の更新プログラムに関するメッセージ")
 
1. **Visual Studio 2019 の更新プログラム**に関するメッセージで、**[詳細の表示]** を選択します。

   ![Visual Studio 2019 IDE の更新プログラムに関するメッセージ内で [詳細の表示] ボタンを選択する](media/vs2019-update-visual-studio-ide-view-details.png "Visual Studio 2019 の更新プログラムに関するメッセージ内で [詳細の表示] ボタンを選択する")

1. **[更新プログラムがダウンロードされてインストールの準備完了]** ダイアログ ボックスで、**[更新]** を選択します。

     ![[更新プログラムがダウンロードされてインストールの準備完了] ダイアログ ボックスで [更新] ボタンを選択する](media/vs2019-update-visual-studio-community-rc-from-ide.png "[更新プログラムがダウンロードされてインストールの準備完了] ダイアログ ボックスで [更新] ボタンを選択する")

   Visual Studio が閉じられてから、再起動されます。

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>関連項目

* [Visual Studio for Mac の更新](/visualstudio/mac/update)

::: moniker-end
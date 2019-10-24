---
title: Spy + + ツールバー |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Spy++ toolbar
ms.assetid: 949c18fb-bb25-42ed-9130-c4a47869f24d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4fa1dfe0917fece3c814678295c5abd6013b426b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72729735"
---
# <a name="spy-toolbar"></a>Spy++ ツール バー
ツールバーは、Spy + + のメニューバーに表示されます。 ツールバーを表示または非表示にするには、 **[表示]** メニューの **[ツールバー]** をクリックします。

 ツールバーでは、次のコントロールを使用できます。

## <a name="uielement-list"></a>UIElement の一覧

|Button|効果|
|------------|------------|
|![Spy&#43; &#43;ウィンドウボタン](../debugger/media/icon_spy--_windows.gif "Icon_Spy + + _Windows")|システム内のウィンドウとコントロールのツリービューを表示します。 詳細については、「 [Windows ビュー](../debugger/windows-view.md)」を参照してください。|
|![Spy&#43; &#43;プロセスボタン](../debugger/media/icon_spy--_processes.gif "Icon_Spy + + プロセス (_d)")|システム内のプロセスのツリービューを表示します。 詳細については、「[プロセスビュー](../debugger/processes-view.md)」を参照してください。|
|![[&#43; &#43; Spy スレッド] ボタン](../debugger/media/icon_spy--_threads.gif "Icon_Spy + + スレッド (_s)")|システム内のスレッドのツリービューを表示します。 詳細については、「[スレッドビュー](../debugger/threads-view.md)」を参照してください。|
|![[&#43; &#43; Spy メッセージ] ボタン](../debugger/media/icon_spy--_messages.gif "Icon_Spy + + メッセージ (_d)")|ウィンドウを作成してウィンドウメッセージを表示し、 **[メッセージオプション]** ダイアログボックスを開いて、メッセージが表示されるウィンドウを選択し、その他のオプションも選択できるようにします。 詳細については、「 [Messages View](../debugger/messages-view.md)」を参照してください。|
|![Spy&#43; &#43;の [ログの開始] ボタン](../debugger/media/icon_spy--_startlog.gif "Icon_Spy + + Startlog")|メッセージログを開始し、メッセージストリームを表示します。 このコントロールは、 **[メッセージ]** ウィンドウがアクティブなウィンドウの場合にのみ使用できます。 詳細については、「[方法: メッセージログの表示を開始および停止する](../debugger/how-to-start-and-stop-the-message-log-display.md)」を参照してください。|
|![Spy&#43; &#43;の [ログの停止] ボタン](../debugger/media/icon_spy--_stoplog.gif "Icon_Spy + + _StopLog")|メッセージのログ記録とメッセージストリームの表示を停止します。 このコントロールは、 **[メッセージ]** ウィンドウがアクティブなウィンドウの場合にのみ使用できます。 詳細については、「[方法: メッセージログの表示を開始および停止する](../debugger/how-to-start-and-stop-the-message-log-display.md)」を参照してください。|
|![[&#43; &#43; Spy ログオプション] ボタン](../debugger/media/icon_spy--_logoptions.gif "Icon_Spy + + _LogOptions")|[[メッセージオプション](../debugger/message-options-dialog-box.md)] ダイアログボックスを表示します。 このダイアログボックスを使用して、表示するウィンドウとメッセージの種類を選択します。 このコントロールは、 **[メッセージ]** ウィンドウがアクティブなウィンドウの場合にのみ使用できます。|
|![Spy&#43; &#43;の [ログのクリア] ボタン](../debugger/media/spy--_clearlog.gif "Spy + + _ClearLog")|[アクティブな**メッセージ**] ウィンドウの内容を消去します。 このコントロールは、 **[メッセージ]** ウィンドウがアクティブなウィンドウの場合にのみ使用できます。|
|![Spy&#43; &#43;検索ウィンドウボタン](../debugger/media/icon_spy--_findwindow.gif "Icon_Spy + + FindWindow (_l)")|[[ウィンドウ](../debugger/find-window-dialog-box.md)の検索] ダイアログボックスを開きます。このダイアログボックスでは、ウィンドウの検索条件を設定したり、プロパティやメッセージを表示したりできます。 詳細については、「[方法: Finder ツールを使用する](../debugger/how-to-use-the-finder-tool.md)」を参照してください。|
|![Spy&#43; &#43;の最初のウィンドウを検索するボタン](../debugger/media/icon_spy--_window.gif "Icon_Spy + + ウィンドウ (_r)")|現在のビューで、一致するウィンドウ、プロセス、スレッド、またはメッセージを検索します。|
|![Spy&#43; &#43;の [次のウィンドウを検索] ボタン](../debugger/media/icon_spy--_nextwindow.gif "Icon_Spy + + Nextwindow (_s)")|現在のビューで、次に一致するウィンドウ、プロセス、スレッド、またはメッセージを検索します。 このコントロール (および関連するメニューコマンド) は、一意ではない有効な検索結果がある場合にのみ使用できます。 たとえば、ウィンドウツリーの検索条件としてウィンドウハンドルを使用すると、ウィンドウツリー内にそのハンドルを持つウィンドウが1つしかないため、一意の結果が生成されます。このインスタンスでは、 **[次を検索**] は使用できません。|
|![Spy&#43; &#43;の [前のウィンドウを検索] ボタン](../debugger/media/icon_spy--_prevwindow.gif "Icon_Spy + + Prevwindow")|現在のビューで、前に一致したウィンドウ、プロセス、スレッド、またはメッセージを検索します。 このコントロール (および関連するメニューコマンド) は、一意ではない有効な検索結果がある場合にのみ使用できます。 たとえば、ウィンドウツリーの検索条件としてウィンドウハンドルを使用すると、ウィンドウツリー内にそのハンドルを持つウィンドウが1つしかないため、一意の結果が生成されます。このインスタンスでは、 **[前を検索]** は使用できません。|
|![Spy&#43; &#43;プロパティエクスプローラーボタン](../debugger/media/icon_spy--_propexp.gif "Icon_Spy + + (_r)")|Windows ビューで選択されているウィンドウのプロパティを表示します。|
|![Spy&#43; &#43;更新ボタン](../debugger/media/icon_spy--_refresh.gif "Icon_Spy + + 更新 (_s)")|システムビューを更新します。|

## <a name="see-also"></a>関連項目
- [Spy++ の使用](../debugger/using-spy-increment.md)
- [Spy++ ビュー](../debugger/spy-increment-views.md)
- [Spy++ リファレンス](../debugger/spy-increment-reference.md)
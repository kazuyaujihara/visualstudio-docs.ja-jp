---
title: メッセージ ビュー |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.externaltools.spyplus.messagesview
helpviewer_keywords:
- Messages view
ms.assetid: 14c2a786-c23a-4b2d-acad-8c32a856c70d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: db9d64119a94e2358a6f52e6e1269fca8d726cbb
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694401"
---
# <a name="messages-view"></a>メッセージ ビュー
各ウィンドウには、関連のメッセージ ストリームがあります。 メッセージ ビュー ウィンドウには、このメッセージのストリームが表示されます。 ウィンドウ ハンドル、メッセージのコードとメッセージが表示されます。 スレッドまたはプロセスもメッセージ ビューを作成することができます。 これにより、特定のプロセスまたはスレッドは初期化のウィンドウ メッセージをキャプチャするために特に便利ですが所有するすべてのウィンドウに送信されるメッセージを表示することができます。

 以下の一般的なメッセージ ビュー ウィンドウが表示されます。 最初の列には、ウィンドウ ハンドルが含まれていますし、2 番目の列には、メッセージ コードが含まれています (で説明されている[メッセージ コード](../debugger/message-codes.md))。 デコードされたメッセージのパラメーターと戻り値が右にします。

 ![Spy&#43; &#43;メッセージ ビューを](../debugger/media/spy--_messagesview.png "スパイ + _MessagesView") spy++ メッセージ ビュー

## <a name="procedures"></a>手順

#### <a name="to-open-a-messages-view-for-a-window-process-or-thread"></a>ウィンドウ、プロセス、またはスレッドのメッセージ ビューを開く

1.  フォーカスを移動する、 [Windows ビュー](../debugger/windows-view.md)、[プロセス ビュー](../debugger/processes-view.md)、または[スレッド ビュー](../debugger/threads-view.md)ウィンドウ。

2.  確認するメッセージが含まれる項目のノードを検索し、それを選択します。

3.  **スパイ**] メニューの [選択**ログ メッセージ**します。

     [メッセージ オプション ダイアログ ボックス](../debugger/message-options-dialog-box.md)が開きます。

4.  メッセージを表示するためのオプションを選択します。

5.  キーを押して**OK**メッセージのログ記録を開始します。

     ビュー ウィンドウが開き、メッセージおよび**メッセージ**spy++ ツールバーにメニューが追加されます。 選択したオプションに応じて、メッセージは、アクティブなメッセージ ビュー ウィンドウにストリーミングを開始します。

6.  十分なメッセージを使用する場合は、選択**ログの停止**から、**メッセージ**メニュー。

## <a name="in-this-section"></a>このセクションの内容
 [メッセージ ビューを制御する](../debugger/how-to-control-messages-view.md)メッセージ ビューを管理する方法について説明します。

 [[検索] ウィンドウからメッセージ ビューを開く](../debugger/how-to-open-messages-view-from-find-window.md)ウィンドウ検索 ダイアログ ボックスからメッセージ ビューを開く方法について説明します。

 [メッセージ ビューでメッセージを探して](../debugger/how-to-search-for-a-message-in-messages-view.md)メッセージ ビューで、特定のメッセージを検索する方法について説明します。

 [開始とメッセージ ログの表示を停止](../debugger/how-to-start-and-stop-the-message-log-display.md)開始およびメッセージのログ記録を停止する方法について説明します。

 [メッセージ コード](../debugger/message-codes.md)メッセージ ビューで表示されているメッセージのコードを定義します。

 [メッセージのプロパティを表示する](../debugger/how-to-display-message-properties.md)メッセージに関する詳細情報を表示する方法。

## <a name="related-sections"></a>関連項目
 [Spy++ ビュー](../debugger/spy-increment-views.md) spy++ ツリー ビュー ウィンドウやメッセージ、プロセス、スレッドのについて説明します。

 [Spy++ の使用](../debugger/using-spy-increment.md)の spy++ ツールを紹介し、使用する方法について説明します。

 [メッセージ オプション ダイアログ ボックス](../debugger/message-options-dialog-box.md)メッセージがアクティブなメッセージ ビューで一覧表示を選択するために使用します。

 [メッセージの検索 ダイアログ ボックス](../debugger/message-search-dialog-box.md)メッセージ ビューで特定のメッセージのノードを検索するために使用します。

 [メッセージのプロパティ ダイアログ ボックス](../debugger/message-properties-dialog-box.md)メッセージ ビューで選択したメッセージのプロパティを表示するために使用します。

 [Spy++ リファレンス](../debugger/spy-increment-reference.md)各 spy++ メニューおよびダイアログ ボックスについて説明するセクションが含まれています。
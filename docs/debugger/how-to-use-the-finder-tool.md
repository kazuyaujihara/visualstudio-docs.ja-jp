---
title: '方法: Finder ツールを使用する |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Window Finder Tool
ms.assetid: 5841926b-08c3-4e43-88bd-4223d04f9aef
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f96fe87137c6b14e32fb2648e93c54a1c5b094a0
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72732173"
---
# <a name="how-to-use-the-finder-tool"></a>方法: ファインダー ツールを使用する
**ウィンドウの検索** ダイアログボックスの ファインダー ツールを使用すると、ウィンドウのプロパティまたはメッセージを表示できます。 ファインダーツールでは、無効になっている子ウィンドウを検索し、無効になっている子ウィンドウが重なっている場合に強調表示するウィンドウを区別することもできます。

 ![[&#43; &#43; Spy 検索ウィンドウ] ダイアログボックス](../debugger/media/icon_spy--_find.png "Icon_Spy + + _Find")[ウィンドウの検索] ダイアログボックスのファインダーツール

 上の図は、次の手順3の後の [ウィンドウの検索] ダイアログボックスを示しています。

### <a name="to-display-window-properties-or-messages"></a>ウィンドウのプロパティまたはメッセージを表示するには

1. Spy + + とターゲットウィンドウの両方が表示されるようにウィンドウを配置します。

2. **[Spy]** メニューの [**ウィンドウの検索]** をクリックします。

    [[ウィンドウの検索] ダイアログボックス](../debugger/find-window-dialog-box.md)が表示されます。

3. **ファインダーツール**をターゲットウィンドウにドラッグします。

    ツールをドラッグすると、 **[ウィンドウの検索]** ダイアログボックスに、選択したウィンドウの詳細が表示されます。

   - または

     確認するウィンドウのハンドル (たとえば、デバッガーからコピーしたもの) がある場合は、 **[ハンドル]** テキストボックスに入力します。

   > [!TIP]
   > 画面を見やすくするには、 **[Spy を隠す]** オプションを選択します。 このオプションを選択すると、メインの Spy + + ウィンドウが非表示になり、他のアプリケーションの上に **[ウィンドウを検索]** ダイアログボックスだけが表示されます。 Spy + + メインウィンドウは、 **[OK]** または **[キャンセル]** をクリックしたとき、または **[Spy + + を非表示]** にする オプションをオフにしたときに復元されます。

4. **[表示]** で、**プロパティ**または**メッセージ**のいずれかを選択します。

5. **[OK]** を押します。

    **[プロパティ]** を選択した場合は、[[ウィンドウのプロパティ] ダイアログボックス](../debugger/window-properties-dialog-box.md)が表示されます。 **メッセージ**を選択した場合は、[[メッセージビュー](../debugger/messages-view.md) ] ウィンドウが開きます。

## <a name="see-also"></a>関連項目
- [Spy++ ビュー](../debugger/spy-increment-views.md)
- [Spy++ の使用](../debugger/using-spy-increment.md)
- [Spy++ リファレンス](../debugger/spy-increment-reference.md)
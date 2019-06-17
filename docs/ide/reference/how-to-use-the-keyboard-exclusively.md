---
title: '方法: キーボード主体で操作する'
description: さまざまな既定のショートカット キーの組み合わせを使って、Visual Studio 統合開発環境 (IDE) 内で移動やコーディングを簡単に行う方法について説明します。
ms.date: 05/10/2019
ms.topic: conceptual
helpviewer_keywords:
- Toolbox, shortcut keys
- shortcut keys [Visual Studio]
- windows [Visual Studio], accessibility
- dialog boxes [Visual Studio], shortcut keys
- keyboard shortcuts [Visual Studio]
- accessibility [Visual Studio]
ms.assetid: d71a4cc1-d352-4164-8538-3f9fa070a331
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5a8759643b9cf72cac671a8d733e1306760afc36
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531601"
---
# <a name="how-to-use-the-keyboard-exclusively"></a>方法: キーボード主体で操作する

キーボード ショートカットを利用すれば、Visual Studio IDE 内での移動とコーディングが簡単になります。 キーボード ショートカットをさらに効果的に利用するための方法をいくつか紹介します。

Visual Studio の全ショートカット キーの一覧については、「[既定のキーボード ショートカット](../../ide/default-keyboard-shortcuts-in-visual-studio.md)」を参照してください。 他の Microsoft 製品で利用できるキーボード ショートカットについては、[https://www.microsoft.com/accessibility/](http://go.microsoft.com/fwlink/?LinkID=40400) をご覧ください。

::: moniker range="vs-2017"

> [!TIP]
> アクセシビリティの更新の詳細については、ブログ記事「[Accessibility improvements in Visual Studio 2017 version 15.3 ](https://devblogs.microsoft.com/visualstudio/accessibility-improvements-in-visual-studio-2017-version-15-3/)」 (Visual Studio 2017 バージョン 15.3 でのアクセシビリティの機能強化) をご覧ください。

::: moniker-end

> [!NOTE]
> 使用している設定または Visual Studio のエディションによっては、ヘルプの記載と異なるダイアログ ボックスやメニュー コマンドが表示される場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[リセット設定](../environment-settings.md#reset-settings)」を参照してください。

## <a name="toolbox-controls"></a>ツールボックス コントロール

キーボードを使って、ツールボックスのコントロールをフォームまたはデザイナーに追加できます。

### <a name="to-add-controls-from-the-toolbox-to-a-designer-from-the-keyboard"></a>キーボードを使ってツールボックスからデザイナーにコントロールを追加するには

1. メニュー バーで **[表示]**、**[ツールボックス]** の順にクリックします。

2. **[ツールボックス]** タブでセクション間を移動するには、**Ctrl キーを押しながら上方向キーを押す**か、**Ctrl キーを押しながら下方向キーを押す**というキーボード ショートカットを使用します。

3. コントロール間を移動するには、**上方向キー**または**下方向キー**を使用します。

4. コントロールを選択した後、**Enter** キーを使用します。

   Visual Studio で、フォームまたはデザイナーにコントロールが追加されます。

## <a name="dialog-box-options"></a>ダイアログ ボックス オプション

 キーボードを使って、ダイアログ ボックスのオプション間を移動し、オプションの設定を変更できます。

### <a name="to-set-dialog-box-options-from-the-keyboard"></a>キーボードを使ってダイアログ ボックスのオプションを設定するには

1. **Tab** キーまたは **Shift**+**Tab** キーを使って、ダイアログ ボックス内のコントロール間を上下に移動します。

2. オプションの設定を変更するには:

    - ラジオ ボタンの場合は、**上方向**キーと**下方向**キーを使って、選択を変更します。

    - チェック ボックスの場合は、**Space キー**を使ってオンまたはオフにします。

    - ドロップダウン リストの場合は、**Alt キーを押しながら下方向キーを押して**項目を表示し、**上方向キー**と**下方向キー**を使って選択した項目を変更します。

    - ボタンの場合は、**Enter** キーを選択して呼び出します。

    - グリッドの場合は、方向キーを使って移動します。 グリッド内のドロップダウン リストの場合は、**Shift** キーと **Alt** キーを押しながら**下方向キー**を押して項目を表示し、**上方向**キーと**下方向**キーを使って選択した項目を変更します。

## <a name="window-and-file-navigation"></a>Windows とファイルのナビゲーション

キーボードを使用し、開いているツール ウィンドウやドキュメント ウィンドウの間を移動するにはいくつかの方法があります。 また、キーボードを使って、ツール ウィンドウを別の場所に移動してドッキングすることもできます。

### <a name="to-navigate-among-windows-and-files-in-the-ide-from-the-keyboard"></a>キーボードを使って IDE 内のウィンドウ間およびファイル間を移動するには

- エディターまたはデザイナー内でファイル間を移動するには、**Ctrl + Tab** ショートカット キーボードを選択し、**[アクティブなファイル]** が選択された IDE ナビゲーターを表示します。 強調表示されているファイルに移動するには、**Enter** キーを押します。

- ドッキングされたツール ウィンドウ間を移動するには、**Alt + F7** キーボード ショートカットを選択し、**[アクティブなツール ウィンドウ]** が選択された IDE ナビゲーターを表示します。 強調表示されているウィンドウに移動するには、**Enter** キーを押します。

### <a name="to-move-and-dock-tool-windows-from-the-keyboard"></a>キーボードを使ってツール ウィンドウを移動してドッキングするには

1. 移動するツール ウィンドウに移動し、フォーカスを設定します。

2. **[ウィンドウ]** メニューで **[ドッキング可能]** オプションを選択します。

3. **Alt**+**Spacebar** キーボード ショートカットを使用し、**[移動]** を選択します。

     ドッキング ガイドのひし形が表示されます。

4. 方向キーを押して、ウィンドウを新しい場所に移動します。

     方向キーを押すと、ウィンドウと共にマウス ポインターが移動します。

5. 新しい場所に到達したら、方向キーを押して、ガイドのひし形の適切な部分にマウス ポインターを移動します。

     新しいドッキング場所にツール ウィンドウの輪郭が表示されます。

6. **Enter** キーを選択します。

     ツール ウィンドウが、新しいドッキング場所の所定の位置にスナップされます。

## <a name="see-also"></a>関連項目

* [キーボード ショートカットの識別とカスタマイズ](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)
* [アクセシビリティのヒントとテクニック](../../ide/reference/accessibility-tips-and-tricks.md)
* [既定のキーボード ショートカット](../../ide/default-keyboard-shortcuts-in-visual-studio.md)

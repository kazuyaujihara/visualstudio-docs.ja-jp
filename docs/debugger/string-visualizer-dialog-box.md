---
title: 文字列ビジュアライザーのダイアログボックス |Microsoft Docs
ms.date: 10/10/2018
ms.custom: seoapril2019
ms.topic: reference
f1_keywords:
- vs.debug.stringviewer
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JavaScript
helpviewer_keywords:
- string visualizer
- visualizers, string
ms.assetid: 080fd8f1-72b0-461f-8451-3c84d5dc51df
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 10e7e50ffc0cb61bd036bef65c554e8147eecc09
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72430823"
---
# <a name="string-visualizer-dialog-box"></a>[String ビジュアライザー] ダイアログ ボックス

Visual Studio でのデバッグ中に、組み込みの文字列ビジュアライザーを使用して文字列を表示できます。 文字列ビジュアライザーは、データヒントまたはデバッガーウィンドウに対して長すぎる文字列を表示します。 また、形式が正しくない文字列を識別するのにも役立ちます。

組み込み文字列ビジュアライザーには、プレーンテキスト、XML、HTML、および JSON オプションが含まれています。 また、 **[自動変数]** ウィンドウまたは他のデバッガーウィンドウから、 [DataSet、DataTable、DataView](../debugger/dataset-visualizer-dialog-box.md)オブジェクトなど、他のいくつかの種類の組み込みビジュアライザーを開くこともできます。

> [!NOTE]
> ビジュアライザーで XAML または WPF UI 要素を検査する必要がある場合は、「[デバッグ中に xaml プロパティ](../xaml-tools/inspect-xaml-properties-while-debugging.md)を調べる」または「 [wpf ツリービジュアライザーを使用する方法](../debugger/how-to-use-the-wpf-tree-visualizer.md)」を参照してください。

文字列ビジュアライザーを開くには、デバッグ中に一時停止する必要があります。 プレーンテキスト、XML、HTML、または JSON 文字列値を持つ変数の上にマウスポインターを移動し、虫眼鏡アイコン![Visualizericon](../debugger/media/dbg-tips-visualizer-icon.png "ビジュアライザーアイコン")を選択します。

## <a name="uielement-list"></a>UIElement の一覧

**[式]** フィールドにカーソルを置いたときの変数または式が表示されます。

**[値]** フィールドには、文字列値が表示されます。 空白の**値**は、選択したビジュアライザーが文字列を認識できないことを意味します。 たとえば、xml**ビジュアライザー**では、xml タグのないテキスト文字列、または JSON 文字列の空白**値**が表示されます。 選択したビジュアライザーが認識できない文字列を表示するには、代わりに**テキストビジュアライザー**を選択します。 **テキストビジュアライザー**にプレーンテキストが表示されます。

### <a name="json-string-data"></a>JSON 文字列データ

Json ビジュアライザーの次の図に示すように、適切な形式の JSON 文字列が表示されます。 間違った形式の JSON では、エラーアイコンが表示される場合があります (認識できない場合は空白です)。 JSON エラーを特定するには、 [JSLint](https://www.jslint.com/)などの json のインラインツールに文字列をコピーして貼り付けます。

![JSON 文字列ビジュアライザー](../debugger/media/dbg-tips-string-visualizer-json.png "JSON 文字列ビジュアライザー")

### <a name="xml-string-data"></a>XML 文字列データ

XML ビジュアライザーの次の図に示すように、整形式の XML 文字列が表示されます。 不適切な形式の XML が XML タグなしで表示されるか、認識されない場合は空白になります。

![XML 文字列ビジュアライザー](../debugger/media/dbg-string-visualizers-xml.png "XML 文字列ビジュアライザー")

### <a name="html-string-data"></a>HTML 文字列データ

次の図に示すように、整形式の HTML 文字列は、ブラウザーに表示されているかのように表示されます。 形式が正しくない HTML は、プレーンテキストとして表示される場合があります。

![HTML 文字列ビジュアライザー](../debugger/media/dbg-string-visualizers-html.png "HTML 文字列ビジュアライザー")

## <a name="see-also"></a>関連項目

- [カスタムビジュアライザー (C#、Visual Basic) の作成](../debugger/create-custom-visualizers-of-data.md)
- [Visual Studio for Mac でのデータの視覚化](/visualstudio/mac/data-visualizations)
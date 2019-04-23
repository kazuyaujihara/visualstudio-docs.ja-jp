---
title: '[String ビジュアライザー] ダイアログ ボックス |Microsoft Docs'
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
ms.openlocfilehash: 982db296fd17fb86b4a139e02a9418eeb507cd91
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59366784"
---
# <a name="string-visualizer-dialog-box"></a>[String ビジュアライザー] ダイアログ ボックス

Visual Studio でデバッグする場合は、組み込みの文字列のビジュアライザーで文字列を表示できます。 文字列ビジュアライザーは、データのヒントやデバッガーのウィンドウ長すぎる文字列を示しています。 形式が正しくない文字列を識別できます。

組み込みの文字列のビジュアライザーには、プレーン テキスト、XML、HTML、および JSON が含まれています。 オプション。 など、他のいくつかの種類では、組み込みのビジュアライザーを開くことも[DataSet、DataTable、および DataView](../debugger/dataset-visualizer-dialog-box.md)オブジェクトから、 **[自動変数]** または他のデバッガー ウィンドウ。

> [!NOTE]
> ビジュアライザーで、XAML または WPF の UI 要素を検査する必要がある場合は、次を参照してください。 または[デバッグ中に XAML の検査プロパティ](../debugger/inspect-xaml-properties-while-debugging.md)または[WPF ツリー ビジュアライザーを使用する方法](../debugger/how-to-use-the-wpf-tree-visualizer.md)します。

文字列のビジュアライザーを開くには、デバッグ中に停止する必要があります。 プレーン テキスト、XML、HTML、または JSON 文字列値、および、虫眼鏡アイコンを選択した変数にマウス![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "ビジュアライザー アイコン")します。

## <a name="uielement-list"></a>UIElement の一覧

**式**変数または式をポイントしているフィールドに表示されます。

**値**フィールドには、文字列値が表示されます。 空白**値**ビジュアライザーを選択したが、文字列を認識できないことを意味します。 たとえば、 **XML ビジュアライザー**は空白を示しています。**値**XML タグのない、テキスト文字列または JSON 文字列。 選択したビジュアライザーを認識できない文字列を表示するには、選択、**テキスト ビジュアライザー**代わりにします。 **テキスト ビジュアライザー**プレーン テキストが表示されます。

### <a name="json-string-data"></a>JSON 文字列データ

JSON のビジュアライザーで、次の図のように、適切な形式の JSON 文字列が表示されます。 正しくない形式の JSON には、エラー アイコン (または認識されない場合は空白) を表示可能性があります。 JSON エラーを識別するためにコピーして貼り付けます、文字列、JSON の lint ツールなど[JSLint](https://www.jslint.com/)します。

![JSON 文字列ビジュアライザー](../debugger/media/dbg-tips-string-visualizer-json.png "JSON 文字列ビジュアライザー")

### <a name="xml-string-data"></a>XML の文字列データ

XML ビジュアライザーで、次の図のように整形式 XML 文字列が表示されます。 形式が正しくない XML は、XML タグ、または空白のない、認識されていない場合に表示します。

![XML 文字列のビジュアライザー](../debugger/media/dbg-string-visualizers-xml.png "XML 文字列のビジュアライザー")

### <a name="html-string-data"></a>HTML 文字列データ

適切な形式の HTML 文字列が表示されますかのように、次の図に示すように、ブラウザーでレンダリングします。 プレーン テキスト形式が正しくない HTML が表示されます。

![HTML 文字列ビジュアライザー](../debugger/media/dbg-string-visualizers-html.png "HTML 文字列ビジュアライザー")

## <a name="see-also"></a>関連項目

- [(C#、Visual Basic) のカスタム ビジュアライザーを作成します。](../debugger/create-custom-visualizers-of-data.md)
- [Visual studio for Mac のデータの視覚化](/visualstudio/mac/data-visualizations)
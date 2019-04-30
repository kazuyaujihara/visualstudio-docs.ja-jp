---
title: デバッグ中に、XPath 式を評価します。
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1585b54d084e3471583f9388d63f5c17e65fc3a7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63002079"
---
# <a name="evaluate-xpath-expressions"></a>XPath 式を評価します。

使用して XPath 式を評価することができます、 **[クイック ウォッチ]** デバッグ中にウィンドウ。 XPath 式は、W3C XPath 1.0 勧告に沿って有効である必要があります。 現在の XSLT コンテキスト (つまり、`self::node()`内のノード、 **[ローカル]** ウィンドウ) XPath 式の評価コンテキストを提供します。

XPath 式を評価する: 場合

- 組み込みの XPath 関数はサポートされます。

- 組み込みの XSLT 関数およびユーザー定義関数はサポートされていません。

> [!NOTE]
> XSLT のデバッグは Visual Studio の Enterprise edition ではできるだけです。

## <a name="evaluate-an-xpath-expression"></a>XPath 式を評価する

次の手順を使用して、 *average.xsl 下*と*books.xml*ファイルから、[チュートリアル。XSLT スタイル シートのデバッグ](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md#sample-files)ページ。

1. `xsl:if` 開始タグにブレークポイントを挿入します。

2. デバッグを開始する**XML** > **XSLT のデバッグの開始**メニュー バーで (または、キーを押して**Alt**+**f5 キーを押して**).

   デバッガーが起動され、`xsl:if` タグで実行が中断されます。

3. 右クリックして **[クイック ウォッチ]** します。

   **[クイック ウォッチ]** ウィンドウが開きます。

4. 入力`./price/text()`で、**式**のフィールド、 **クイック ウォッチ**  ダイアログ ボックスを選び、**再評価**します。

   現在の book ノードの価格が表示されます、**値**ボックス。

   ![[クイック ウォッチ] ウィンドウで、XPath 式を評価します。](media/quickwatch-price.png)

5. XPath 式を変更`./price/text() < $bookAverage`クリック**再評価**。

   **値**ボックスが表示されます、XPath 式の評価が`true`します。

## <a name="see-also"></a>関連項目

- [XSLT のデバッグ](../xml-tools/debugging-xslt.md)
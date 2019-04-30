---
title: XSLT スタイル シートをデバッグします。
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 3db9fa5a-f619-4cb6-86e7-64b364e58e5d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e787ca3d2d29f04d6af27a5f36f1f84c9d0bc9f4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62808479"
---
# <a name="walkthrough-debug-an-xslt-style-sheet"></a>チュートリアル: XSLT スタイル シートのデバッグ

このチュートリアルの手順では、XSLT デバッガーを使用する方法を示します。 変数の表示、ブレークポイントの設定、コードのステップ実行などの手順が含まれます。 デバッガーでは、一度に 1 行のコードを実行することができます。

このチュートリアルの準備として、まず、2 つをコピー[サンプル ファイル](#sample-files)をローカル コンピューターにします。 1 つは、スタイル シート、および 1 つは、XML ファイル、スタイル シートへの入力として使用します。 このチュートリアルで使用してスタイル シートはコストが、平均書籍価格を下回るすべてのブックを検索します。

> [!NOTE]
> XSLT デバッガーには、Visual Studio の Enterprise edition ではできるだけです。

## <a name="start-debugging"></a>[デバッグ開始]

1. **ファイル**] メニューの [選択**オープン** > **ファイル**します。

2. 検索、 *average.xsl 下*ファイル**オープン**します。

   スタイル シートは、XML エディターで開きます。

3. 参照 ボタンをクリックします (**.**) で、**入力**ドキュメントのプロパティ ウィンドウのフィールド。 (場合、**プロパティ**ウィンドウが表示されない、エディターで開いているファイルを右クリックし、**プロパティ**)。

4. 検索、 *books.xml*ファイルを選び、**オープン**します。

   これには、XSLT 変換に使用されるソース ドキュメント ファイルを設定します。

5. 設定、[ブレークポイント](../debugger/using-breakpoints.md)の 12 行目*average.xsl 下*します。 これには複数の方法のいずれかの操作を行うことができます。

   - 12 行目で、エディターの余白をクリックします。

   - 、12 行目の部分をクリックして、キーを押します**F9**します。

   - 右クリックし、`xsl:if`開始タグを選び、**ブレークポイント** > **ブレークポイントの挿入**します。

      ![Visual Studio での XSL ファイルでブレークポイントを挿入します。](media/insert-breakpoint.PNG)

6. メニュー バーで、 **XML** > **XSLT のデバッグの開始**(または、キーを押します**Alt**+**F5**)。

   デバッグ プロセスを開始します。

   エディターで、デバッガーが配置されている、`xsl:if`スタイル シートの要素。 という別のファイル*average.xml 下*; エディターで開きますこれは、入力ファイル内の各ノードとして挿入される出力ファイル*books.xml*処理されます。

   **[自動変数]**、**ローカル**、および**ウォッチ 1** Visual Studio ウィンドウの下部にあるウィンドウが表示されます。 **ローカル**ウィンドウは、すべてのローカル変数とその現在の値が表示されます。 ここには、スタイル シートで定義されている変数や、コンテキスト内に現在存在するノードを追跡するためにデバッガーが使用する変数なども表示されます。

## <a name="watch-window"></a>[ウォッチ] ウィンドウ

2 つの変数を追加します、**ウォッチ 1**ウィンドウため、入力ファイルが処理されると、その値を確認できますの。 (使用することも、**ローカル**ウォッチする変数は、既にある場合は、値を確認するウィンドウ)。

1. **デバッグ**] メニューの [選択**Windows** > **ウォッチ** > **ウォッチ 1**します。

   **ウォッチ 1**ウィンドウが表示されるようになります。

2. 型`$bookAverage`で、**名前**フィールド、およびキーを押します**Enter**します。

   値、`$bookAverage`で変数が表示されます、**値**フィールド。

3. 次の行に入力`self::node()`で、**名**フィールド、およびキーを押します**Enter**します。

   `self::node()` は、現在のコンテキスト ノードに評価される XPath 式です。 `self::node()` XPath 式の値は、最初の book ノードです。 この値は、変換処理の進行につれて変化します。

4. 展開、`self::node()`ノード、ノードを展開し、ユーザーが値は`price`します。

   ![Visual Studio で XSLT のデバッグ中に [ウォッチ] ウィンドウ](media/xslt-debugging-watch-window.png)

   現在の book ノードの書籍の価格の値を参照してくださいし、比較することができます、`$bookAverage`値。 書籍の価格が、平均より下にあるため、`xsl:if`デバッグ プロセスを続行する条件が成功します。

## <a name="step-through-the-code"></a>コードをステップ実行

1. **F5** キーを押して続行します。

   最初の book ノードが満たされているため、`xsl:if`条件、book ノードに追加されます、 *average.xml 下*出力ファイル。 デバッガーは、再度スタイル シートの `xsl:if` 要素に到達するまで、引き続き実行されます。 デバッガーは現在、2 番目の book ノードに配置されて、 *books.xml*ファイル。

   **ウォッチ 1**ウィンドウで、`self::node()`値が 2 番目の book ノードに変更します。 price 要素の値を調べることで、価格が平均値より高いことを判断できるため、`xsl:if` 条件は失敗します。

2. **F5** キーを押して続行します。

   2 番目の book ノードを満たしていないため、`xsl:if`条件には、この book ノードは追加されていない、 *average.xml 下*出力ファイル。 デバッガーは引き続きでもう一度配置されるまでの実行、`xsl:if`スタイル シート内の要素。 デバッガーの 3 番目の位置は今すぐ`book`内のノード、 *books.xml*ファイル。

   **ウォッチ 1**ウィンドウで、`self::node()`値は 3 番目の book ノードに変更します。 値を調べることで、`price`要素、平均値より価格が決定できます。 `xsl:if`条件が成功する必要があります。

3. **F5** キーを押して続行します。

   `xsl:if`条件が満たされて、3 番目の book を追加する、 *average.xml 下*出力ファイル。 XML ドキュメント内の書籍がすべて処理され、デバッガーが停止します。

## <a name="sample-files"></a>サンプル ファイル

このチュートリアルでは、次の 2 つのファイルを使用します。

### <a name="below-averagexsl"></a>below-average.xsl

```xml
<?xml version='1.0'?>
<xsl:stylesheet version="1.0"
      xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output method="xml" encoding="utf-8"/>
  <xsl:template match="/">
    <xsl:variable name="bookCount" select="count(/bookstore/book)"/>
    <xsl:variable name="bookTotal" select="sum(/bookstore/book/price)"/>
    <xsl:variable name="bookAverage" select="$bookTotal div $bookCount"/>
    <books>
      <!--Books That Cost Below Average-->
      <xsl:for-each select="/bookstore/book">
        <xsl:if test="price &lt; $bookAverage">
          <xsl:copy-of select="."/>
        </xsl:if>
      </xsl:for-each>
    </books>
  </xsl:template>
</xsl:stylesheet>
```

### <a name="booksxml"></a>books.xml

```xml
<?xml version='1.0'?>
<!-- This file represents a fragment of a book store inventory database -->
<bookstore>
  <book genre="autobiography" publicationdate="1981" ISBN="1-861003-11-0">
    <title>The Autobiography of Benjamin Franklin</title>
    <author>
      <first-name>Benjamin</first-name>
      <last-name>Franklin</last-name>
    </author>
    <price>8.99</price>
  </book>
  <book genre="novel" publicationdate="1967" ISBN="0-201-63361-2">
    <title>The Confidence Man</title>
    <author>
      <first-name>Herman</first-name>
      <last-name>Melville</last-name>
    </author>
    <price>11.99</price>
  </book>
  <book genre="philosophy" publicationdate="1991" ISBN="1-861001-57-6">
    <title>The Gorgias</title>
    <author>
      <name>Plato</name>
    </author>
    <price>9.99</price>
  </book>
</bookstore>
```

## <a name="see-also"></a>関連項目

- [XSLT のデバッグ](../xml-tools/debugging-xslt.md)
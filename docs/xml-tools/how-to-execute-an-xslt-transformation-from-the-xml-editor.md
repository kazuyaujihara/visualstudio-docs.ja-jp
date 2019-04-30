---
title: XSLT 変換を実行します。
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 56a0fe82-5231-487d-8b6e-a08a9b04e0fc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e84b1c6303da4c0db39da1b3585a7d4548560feb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63001938"
---
# <a name="how-to-execute-an-xslt-transformation-from-the-xml-editor"></a>方法: XML エディターから XSLT 変換を実行する

XML エディターでは、XSLT スタイル シートを XML ドキュメントに関連付ける、変換を実行し、出力を表示することができます。 XSLT 変換から得られた結果の出力は、新しいドキュメント ウィンドウに表示されます。

**出力**プロパティは、出力ファイル名を指定します。 場合、**出力**プロパティが空白の一時ディレクトリにファイル名が生成されます場合、。 ファイル拡張子がに基づいて、`xsl:output`要素のスタイル シート *。xml*、.*txt*または *。htm*します。

場合、**出力**プロパティを持つファイル名を指定します、 *。htm*または *。html*拡張 XSLT 出力が web ブラウザーを使用してプレビューを表示します。 Visual Studio によって選択された既定のエディターを使用して、その他のすべてのファイル拡張子が開かれます。 たとえば、ファイル拡張子がある場合です。*xml*、Visual Studio は、XML エディターを使用します。

## <a name="execute-an-xslt-transformation-from-an-xml-file"></a>XML ファイルから XSLT 変換を実行します。

1. XML エディターで XML ドキュメントを開きます。

2. XSLT スタイル シートを XML ドキュメントと関連付けます。

    - XML ドキュメントに `xml-stylesheet` 処理命令を追加します。 たとえば、ドキュメントのプロローグに次の行を追加します。 `<?xml-stylesheet type='text/xsl' href='filename.xsl'?>`

       - または -

    - XSLT スタイル シートを使用して、追加、**プロパティ**ウィンドウ。 XML ファイルをエディターで開いて、エディター内を右クリックし、選択**プロパティ**します。 **プロパティ**ウィンドウでをクリックし、 **Stylesheet**フィールドし、参照ボタン (...) を選択します。XSLT スタイル シートを選択し、**オープン**します。

3. メニュー バーで、 **XML** > **デバッグせずに XSLT を開始**します。 または、キーを押して**Ctrl**+**Alt**+**f5 キーを押して**します。

   XSLT 変換からの出力は、新しいドキュメント ウィンドウに表示されます。

   > [!NOTE]
   > XML ドキュメントに関連付けられているスタイル シートがない場合は、使用するスタイル シートの指定を求めるダイアログ ボックスが表示されます。

## <a name="execute-an-xslt-transformation-from-an-xslt-style-sheet"></a>XSLT スタイル シートから XSLT 変換を実行します。

1. XSLT スタイル シートを XML エディターで開きます。

2. 内の XML ドキュメントの指定、**入力**ドキュメントのフィールド**プロパティ**ウィンドウ。

   > [!NOTE]
   > この XML ドキュメントは、変換に使用する入力ドキュメントです。 XSLT 変換が開始されると、ドキュメントが指定されていない場合、**ファイルを開く** ダイアログ ボックスが表示され、その時点でドキュメントを指定することができます。

3. メニュー バーで、 **XML** > **デバッグせずに XSLT を開始**します。 または、キーを押して**Ctrl**+**Alt**+**f5 キーを押して**します。

   XSLT 変換からの出力は、新しいドキュメント ウィンドウに表示されます。

## <a name="specify-an-output-file-name"></a>出力ファイル名を指定します。

XML と XSL の両方のファイルの出力ファイル名を指定することができます。 開く、**プロパティ**ウィンドウで、ファイル名を指定し、**出力**フィールド。

## <a name="see-also"></a>関連項目

- [XML エディター](../xml-tools/xml-editor.md)
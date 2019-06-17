---
title: XML エディターおよびスキーマ デザイナー
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vb.xmldesigner
helpviewer_keywords:
- XML [Visual Studio], resources
- Enterprise Templates, XML and
- discovery files, XML
- server controls, XML and
- Web server controls, XML
- XSL
- XML [Visual Studio], data sources
- XML schemas
- XML [Visual Studio], SGML relationship to
- CSS, style sheets for XML
- XML [Visual Studio], .NET classes
- data [Visual Studio], XML
- classes [Visual Studio], XML
- style sheets, for XML
- Web services
- SGML, XML
- XML [Visual Studio]
- datasets [Visual Basic], XML Schemas
- XSD schemas
- XSL, style sheets
- XMLDataDocument class
ms.assetid: 1fd5de47-2d61-4180-9539-c2c4bf9ab768
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d7493d6c10c83b16ad7579299a49a7747e34c20b
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2019
ms.locfileid: "66746517"
---
# <a name="xml-tools-in-visual-studio"></a>Visual Studio の XML ツール

*拡張マークアップ言語 (XML)* マークアップ言語であり、データを記述する形式を提供します。 XML データを分離して、Extensible Stylesheet Language (XSL) などのスタイル シートやカスケード スタイル シート (CSS) を使用して、プレゼンテーションが関連付けられています。 Visual Studio には、XML、XSLT、および XML スキーマの操作を容易にするツールと機能が含まれています。

## <a name="xml-editor"></a>XML エディター

[XML エディター](xml-editor.md) XML ドキュメントを編集するために使用します。 完全な XML 構文チェック、入力、色分け、および IntelliSense の中に、スキーマ検証を提供します。 スキーマまたはドキュメント型定義が提供された場合は IntelliSense によって使用され、使用可能な要素と属性が一覧で示されます。

次のような機能も含まれています。

- スキーマから生成されるスニペットを含めた、XML スニペットのサポート

- ドキュメントの要素を展開し、折りたたまれているようにをアウトライン表示

- XSLT 変換を実行し、テキスト、XML、または HTML として結果を表示するには

- XML インスタンス ドキュメントから XML スキーマ定義言語 (XSD) スキーマを生成する機能

- IntelliSense のサポートを含む、XSLT スタイル シートを編集するためのサポート

- XML スキーマ エクスプローラー

## <a name="xml-schema-designer"></a>XML スキーマ デザイナー

[XML スキーマ デザイナー](xml-schema-designer.md) XML スキーマ定義言語 (XSD) スキーマを使用することを有効にするには、Visual Studio と XML エディターと統合されています。

## <a name="xslt-debugging"></a>XSLT のデバッグ

Visual Studio では[XSLT スタイル シートをデバッグ](../xml-tools/debugging-xslt.md)します。 デバッガーを使用すると、XSLT スタイル シート内のブレークポイントの設定や、コードから XSLT スタイル シートへのステップ インなどが可能になります。

> [!NOTE]
> XSLT デバッガーには、Visual Studio の Enterprise edition ではできるだけです。

## <a name="see-also"></a>関連項目

- <xref:System.Xml?displayProperty=fullName>
- [XSLT 変換](/dotnet/standard/data/xml/xslt-transformations)
- [XPath データ モデルを使用して XML データの処理](/dotnet/standard/data/xml/process-xml-data-using-the-xpath-data-model)
- [XML ドキュメント オブジェクト モデル (DOM)](/dotnet/standard/data/xml/xml-document-object-model-dom)
- [XML スキーマ オブジェクト モデル (SOM)](/dotnet/standard/data/xml/xml-schema-object-model-som)
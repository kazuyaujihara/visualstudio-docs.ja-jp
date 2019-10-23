---
title: Xml リテラルと XML スキーマエクスプローラーの統合 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 57a29998-c6e8-48ac-bdb0-5788e73f9164
caps.latest.revision: 10
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d45b7917f5e92f20ec7d7c896c2dc9540a9554e0
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656281"
---
# <a name="integration-of-xml-literals-with-xml-schema-explorer"></a>XML リテラルと XML スキーマ エクスプローラーの統合
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Basic では XML リテラルがサポートされているため、Visual Basic コードに XML フラグメントを直接組み込むことができます。 詳細については、「 [XML リテラルの概要](http://go.microsoft.com/fwlink/?LinkId=140325)」を参照してください。

 Visual Basic プロジェクトの XSD ファイルに XML リテラルが含まれる場合、XML スキーマ エクスプローラーで XML スキーマ セットを表示できます。 XML リテラルに関連付けられているスキーマセットを表示するには、xml リテラルまたは XML 名前空間インポートで XML ノードを右クリックし、 **[スキーマエクスプローラーで表示]** を選択します。

 ![XML リテラルを Visual Basic します。XML スキーマエクスプローラー](../xml-tools/media/vbxmlliteralswithxmlschemaexplorer1.gif "VBXMLLiteralsWithXMLSchemaExplorer1")

 これにより、XML スキーマ エクスプローラーが Visual Basic ファイルと並んで表示されます。

 ![XML リテラルを Visual Basic します。XML スキーマエクスプローラー](../xml-tools/media/vbxmlliteralswithxmlschemaexplorer2.gif "VBXMLLiteralsWithXMLSchemaExplorer2")

 この機能は Visual Studio 2008 SP1 で導入されました。 この機能の詳細については、「 [Channel 9 インタビュー: Visual Studio 2008 SP1 の XML スキーマエクスプローラー](https://channel9.msdn.com/Blogs/funkyonex/XML-Schema-Explorer-in-Visual-Studio-2008-SP1)」を参照してください。

## <a name="see-also"></a>参照
 [方法: XML リテラルに XML スキーマ デザイナーを使用する](../xml-tools/how-to-use-the-xml-schema-designer-with-xml-literals.md)

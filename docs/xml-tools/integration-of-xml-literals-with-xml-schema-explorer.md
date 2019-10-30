---
title: XML リテラルと XML スキーマ エクスプローラーの統合
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 57a29998-c6e8-48ac-bdb0-5788e73f9164
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cf073145b0deb21a2ec29ac1fff16be08fb24593
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72986302"
---
# <a name="integration-of-xml-literals-with-xml-schema-explorer"></a>Xml リテラルと XML スキーマエクスプローラーの統合

Visual Basic では XML リテラルがサポートされているため、Visual Basic コードに XML フラグメントを直接組み込むことができます。 詳細については、「 [XML リテラルの概要](/dotnet/visual-basic/programming-guide/language-features/xml/xml-literals-overview)」を参照してください。

## <a name="how-to"></a>方法

Visual Basic プロジェクト内の XSD ファイルに XML リテラルが含まれている場合は、xml スキーマ**エクスプローラー**で xml スキーマセットを表示できます。 XML リテラルに関連付けられているスキーマセットを表示するには、xml リテラルまたは XML 名前空間インポートで XML ノードを右クリックし、 **[スキーマエクスプローラーで表示]** を選択します。

![Visual Basic XML リテラル (XML スキーマ エクスプローラー)](../xml-tools/media/vbxmlliteralswithxmlschemaexplorer1.gif)

これにより、 **XML スキーマエクスプローラー**が Visual Basic ファイルと並行して開きます。

![Visual Basic XML リテラル (XML スキーマ エクスプローラー)](../xml-tools/media/vbxmlliteralswithxmlschemaexplorer2.gif)

## <a name="see-also"></a>関連項目

- [方法: xml リテラルで XML スキーマデザイナーを使用する](../xml-tools/how-to-use-the-xml-schema-designer-with-xml-literals.md)
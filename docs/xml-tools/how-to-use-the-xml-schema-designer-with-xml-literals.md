---
title: '方法: XML リテラルに XML スキーマ デザイナーを使用する'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d11803e7-f81a-41a2-a145-ba494a45cc93
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 9e92cbdca3ac2c5c366ec054ba79f2e7324986c1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63001819"
---
# <a name="how-to-use-the-xml-schema-designer-with-xml-literals"></a>方法: XML リテラルに XML スキーマ デザイナーを使用する

このトピックでは、Visual Basic プロジェクトの XML リテラルに関連付けられたスキーマを表示する方法について説明します。

## <a name="create-a-new-visual-basic-project"></a>新しい Visual Basic プロジェクトを作成します。

1. Visual Studio を開きます。

2. 新しい Visual Basic 作成**コンソール アプリ**という名前のプロジェクト**XMLLiterals**します。

     新しいプロジェクトには、1 つの Visual Basic ソース ファイルが含まれています。 *Module1.vb*します。

## <a name="add-an-existing-xsd-file"></a>既存の XSD ファイルを追加します。

1. メモ帳で新しいテキスト ファイルを開きます。 XML スキーマのサンプル コードをコピー[購買発注書のスキーマ](../xml-tools/sample-xsd-file-simple-schema.md)ファイルに貼り付けます。

2. いくつかの場所に名前でファイルを保存*PurchaseOrderSchema.xsd*します。

3. **ソリューション エクスプ ローラー**、プロジェクトの名前を右クリックし、選択**追加**、し、**既存項目の**します。 **既存項目の追加** ダイアログ ボックスが表示されます。 参照、 *PurchaseOrderSchema.xsd*ファイル、それを選択してクリックして**追加**します。

     XMLLiterals プロジェクトには、2 つのファイルが含まれています。*Module1.vb*と*PurchaseOrderSchema.xsd*します。

## <a name="add-code"></a>コードを追加します。

Xml リテラルには、Visual Basic コードを追加するには、プロジェクトに含まれる XSD ファイルに基づいています。

1. コードに置き換えます*Module1.vb*を次のコード ファイル。

   ```vb
   Imports <xmlns:ns="http://tempuri.org/PurchaseOrderSchema.xsd">

   Module Module1
      Sub Main()

          Dim XMLLiteral = <ns:PurchaseOrder OrderDate="1900-01-01">
                               <ns:ShipTo country="US">
                                   <ns:name>name1</ns:name>
                                   <ns:street>street1</ns:street>
                                   <ns:city>city1</ns:city>
                                   <ns:state>state1</ns:state>
                                   <ns:zip>1</ns:zip>
                               </ns:ShipTo>
                               <ns:BillTo country="US">
                                   <ns:name>name1</ns:name>
                                   <ns:street>street1</ns:street>
                                   <ns:city>city1</ns:city>
                                   <ns:state>state1</ns:state>
                                   <ns:zip>1</ns:zip>
                               </ns:BillTo>
                           </ns:PurchaseOrder>

      End Sub
   End Module
   ```

2. XML リテラルまたは XML 名前空間インポートでの任意の XML ノードを右クリックして**スキーマ エクスプ ローラーで表示する**します。

   **XML スキーマ エクスプ ローラー**が XML スキーマのセットに関連付けられた XML リテラルのある Visual Basic ファイルと並んで表示されます。
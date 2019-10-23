---
title: '方法: XSD スキーマに基づいて XML ドキュメントを作成する'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1f423af7dc4fae7a116acbaf8497c5ee4268653e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72645975"
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>方法: XSD スキーマに基づいて XML ドキュメントを作成する

**[サンプル xml の生成]** 機能では、xml スキーマ (XSD) ファイルに基づいてサンプルの xml ファイルが生成されます。

このオプションは、次のようなシナリオで使用できます。

- スキーマのさまざまな構造の使用法を理解する。

- スキーマが意図したとおりに機能しているかどうかを確認する。

**[サンプル XML の生成]** 機能は、グローバル要素でのみ使用でき、有効な xml スキーマセットが必要です。

この機能では、通常は有効な XML ドキュメントが生成されます。 ただし、スキーマに次のものが 1 つ以上含まれていると、有効なサンプルが生成されない可能性があります。

- `xs:key`、`xs:keyref`、および `xs:unique` の ID 制約

- `xs:pattern` ファセット

- `xs:QName` 型の列挙

- `xs:ENTITY` 型、`xs:ENTITIES` 型、および `xs:NOTATION` 型

また、`xs:base64Binary` の内容は、その型のスキーマで列挙が発生する場合にのみ生成されることに注意してください。

## <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>XSD ファイルに基づいて XML インスタンス ドキュメントを生成するには

1. [「方法: XSD スキーマファイルを作成および編集する](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)」の手順に従います。

2. [XML スキーマエクスプローラー](../xml-tools/xml-schema-explorer.md)で、`PurchaseOrder` グローバル要素を右クリックします。 **[サンプル XML の生成]** を選択します。

     このオプションを選択すると、PurchaseOrder が表示されます。次のサンプル XML コンテンツを含む*xml*ファイルが生成され、xml エディターで開かれます。

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <PurchaseOrder OrderDate="1900-01-01" xmlns="http://tempuri.org/PurchaseOrderSchema.xsd">
      <ShipTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </ShipTo>
      <ShipTo country="US">
        <name>name2</name>
        <street>street2</street>
        <city>city2</city>
        <state>state2</state>
        <zip>-79228162514264337593543950335</zip>
      </ShipTo>
      <BillTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </BillTo>
    </PurchaseOrder>
    ```
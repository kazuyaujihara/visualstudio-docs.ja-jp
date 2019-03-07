---
title: XML スニペット
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 348dbf64-3f09-4fff-b47a-a7ecdf3221cc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66736431b295f974bda1ca855d88cd5f5f868e7d
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526156"
---
# <a name="xml-snippets"></a>XML スニペット

XML エディターと呼ばれる、機能を提供する*XML スニペット*、XML ファイルをより迅速にビルドすることができます。 XML スニペットは、ファイルに挿入することで再利用できます。 XML スキーマ定義言語 (XSD) スキーマに基づいて XML データを生成することもできます。

## <a name="reusable-xml-snippets"></a>再利用可能な XML スニペット

XML エディターには、一般的なタスクを対象とした多くのスニペットが含まれています。 これによって、XML ファイルをより簡単に作成できます。 たとえば、XML スキーマを作成して、"Complex Type Sequence Element"と"Simple Type Element"スニペットを使用してはファイルに次の XML テキストに挿入します。 その後で、必要に応じて `name` の値を変更します。

```xml
<xs:element name="name">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="name">
        <xs:simpleType>
          <xs:restriction base="xs:string"></xs:restriction>
        </xs:simpleType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

スニペットは 2 つの方法で挿入できます。 **スニペットの挿入**コマンドは、カーソル位置にある XML スニペットを挿入します。 **ブロックの挿入**コマンドは、選択したテキストの周囲の XML スニペットをラップします。 両方のコマンドが使用可能ないずれかから、 **IntelliSense**サブメニュー、**編集**メニューで、またはエディター内で右クリック メニューから。

詳細については、「[方法 :XML スニペットを使用する](../xml-tools/how-to-use-xml-snippets.md)します。

## <a name="schema-generated-xml-snippets"></a>スキーマから生成される XML スニペット

XML エディターでは、XML スキーマから XML スニペットを生成する機能もあります。 この機能を使用すると、要素に、その要素のスキーマ情報から生成された XML 要素を格納することができます。 詳細については、「[方法 :XML スキーマから XML スニペットを生成](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)します。

## <a name="create-new-xml-snippets"></a>新しい XML スニペットを作成します。

既定では、Visual Studio に含まれているスニペットに加えても作成し、独自の XML スニペットを使用できます。 詳細については、「[方法 :XML スニペットを作成する](../xml-tools/how-to-create-xml-snippets.md)します。

## <a name="see-also"></a>関連項目

- [Visual Studio のコード スニペット](../ide/code-snippets.md)
- [XML エディター](../xml-tools/xml-editor.md)
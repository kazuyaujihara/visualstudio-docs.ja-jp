---
title: 'CA1028: 列挙ストレージは Int32 | である必要がありますMicrosoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: fc1039cb547a48c4f2dd3ea869b46d4706e9c3a2
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661904"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: 列挙ストレージは Int32 でなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリック列挙型の基になる型が <xref:System.Int32?displayProperty=fullName> ません。

## <a name="rule-description"></a>規則の説明
 列挙型は、関連する名前付き定数が複数定義された値型です。 既定では、定数値を格納するために、<xref:System.Int32?displayProperty=fullName> データ型が使用されます。 この基になる型を変更することはできますが、ほとんどのシナリオでは必須ではなく、推奨もされません。 @No__t_0 よりも小さいデータ型を使用した場合、パフォーマンスは大幅に向上しないことに注意してください。 既定のデータ型を使用できない場合は、共通言語システム (CLS) に準拠している整数型 (<xref:System.Byte>、<xref:System.Int16>、<xref:System.Int32>、または <xref:System.Int64>) のいずれかを使用して、列挙体のすべての値を CLS 準拠のプログラミングで表現できることを確認する必要があります。言語。

## <a name="how-to-fix-violations"></a>違反の修正方法
 サイズや互換性の問題が存在しない場合は、この規則違反を修正するには、<xref:System.Int32> を使用します。 @No__t_0 が値を保持するのに十分な大きさでない場合は、<xref:System.Int64> を使用します。 旧バージョンとの互換性のためにより小さいデータ型が必要な場合は、<xref:System.Byte> または <xref:System.Int16> を使用します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 旧バージョンとの互換性の問題に必要な場合にのみ、この規則の警告を非表示にします。 アプリケーションでは、この規則に準拠していないと、通常、問題は発生しません。 言語の相互運用性が必要なライブラリでは、この規則に準拠していないと、ユーザーに悪影響を及ぼす可能性があります。

## <a name="example-of-a-violation"></a>違反の例

### <a name="description"></a>説明
 次の例は、推奨される基になるデータ型を使用しない2つの列挙を示しています。

### <a name="code"></a>コード
 [!code-csharp[FxCop.Design.EnumIntegralType#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/cs/FxCop.Design.EnumIntegralType.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralType#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/vb/FxCop.Design.EnumIntegralType.vb#1)]

## <a name="example-of-how-to-fix"></a>修正方法の例

### <a name="description"></a>説明
 次の例では、基になるデータ型を <xref:System.Int32> に変更することで、以前の違反を修正します。

### <a name="code"></a>コード
 [!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/cs/FxCop.Design.EnumIntegralTypeFixed.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/vb/FxCop.Design.EnumIntegralTypeFixed.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1008: Enums は 0 値を含んでいなければなりません](../code-quality/ca1008-enums-should-have-zero-value.md)

 [CA1027: FlagsAttribute で列挙値をマークします](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: enums を FlagsAttribute に設定しません](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1700: enum 値に 'Reserved' という名前を指定しません](../code-quality/ca1700-do-not-name-enum-values-reserved.md)

 [CA1712: enum 値を型名のプレフィックスにしません](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>参照
 <xref:System.Byte?displayProperty=fullName> <xref:System.Int16?displayProperty=fullName>
 <xref:System.Int32?displayProperty=fullName>
 <xref:System.Int64?displayProperty=fullName>

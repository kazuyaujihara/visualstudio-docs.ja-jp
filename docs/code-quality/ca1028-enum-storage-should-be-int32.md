---
title: CA1028:列挙ストレージは Int32 でなければなりません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 47a934a6e35296927eea64465ff8e7007219bec5
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236095"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028:列挙ストレージは Int32 でなければなりません

|||
|-|-|
|TypeName|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

列挙型の基になる型が<xref:System.Int32?displayProperty=fullName>ではありません。

既定では、この規則はパブリック列挙のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

列挙型は、関連する名前付き定数が複数定義された値型です。 既定では、 <xref:System.Int32?displayProperty=fullName>データ型は定数値を格納するために使用されます。 この基になる型を変更することはできますが、ほとんどのシナリオでは必須ではなく、推奨もされません。 より<xref:System.Int32>小さいデータ型を使用すると、パフォーマンスが大幅に向上することはありません。 既定のデータ型を使用できない場合は、共通言語システム (CLS) に準拠している<xref:System.Byte>整数型、 <xref:System.Int32>、 <xref:System.Int16>、、または<xref:System.Int64>のいずれかを使用して、列挙体のすべての値をで表すことができるようにする必要があります。CLS 準拠のプログラミング言語。

## <a name="how-to-fix-violations"></a>違反の修正方法

サイズや互換性の問題が存在する場合を除き、この規則違反を<xref:System.Int32>修正するには、を使用します。 <xref:System.Int32>が値を保持するのに十分な大きさでない場合<xref:System.Int64>は、を使用します。 旧バージョンとの互換性のためにより小さい<xref:System.Byte>データ<xref:System.Int16>型が必要な場合は、またはを使用します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

旧バージョンとの互換性の問題に必要な場合にのみ、この規則の警告を非表示にします。 アプリケーションでは、この規則に準拠していないと、通常、問題は発生しません。 言語の相互運用性が必要なライブラリでは、この規則に準拠していないと、ユーザーに悪影響を及ぼす可能性があります。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1028.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example-of-a-violation"></a>違反の例

次の例は、推奨される基になるデータ型を使用しない2つの列挙を示しています。

[!code-vb[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_1.vb)]
[!code-csharp[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_1.cs)]

## <a name="example-of-how-to-fix"></a>修正方法の例

次の例では、基になるデータ型をに変更<xref:System.Int32>することで、以前の違反を修正します。

[!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_2.cs)]
[!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_2.vb)]

## <a name="related-rules"></a>関連するルール

- [CA1008列挙型の値は0である必要があります](../code-quality/ca1008-enums-should-have-zero-value.md)
- [CA1027FlagsAttribute で列挙をマークする](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217FlagsAttribute で列挙をマークしない](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)
- [CA1700列挙値に ' Reserved ' という名前を指定することはできません](../code-quality/ca1700-do-not-name-enum-values-reserved.md)
- [CA1712列挙値の型名をプレフィックスとして使用しない](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>関連項目

- <xref:System.Byte?displayProperty=fullName>
- <xref:System.Int16?displayProperty=fullName>
- <xref:System.Int32?displayProperty=fullName>
- <xref:System.Int64?displayProperty=fullName>
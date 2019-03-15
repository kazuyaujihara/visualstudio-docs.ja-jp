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
ms.openlocfilehash: 95e2a8892bb7b52122dd34afa3f300123149bb26
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57871851"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028:列挙ストレージは Int32 でなければなりません

|||
|-|-|
|TypeName|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

列挙体の基になる型でない<xref:System.Int32?displayProperty=fullName>します。

既定では、このルールだけを確認、パブリック列挙型が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

列挙型は、関連する名前付き定数が複数定義された値型です。 既定で、<xref:System.Int32?displayProperty=fullName>定数の値を格納するデータ型を使用します。 できます、この変更の種類を基になる場合でもないために必要なまたは推奨されるほとんどのシナリオ。 小さいデータ型を使用して大幅なパフォーマンスの向上が実現しない<xref:System.Int32>します。 既定のデータ型を使用できない場合、共通言語システム (CLS) のいずれかを使用する必要があります-準拠の整数型<xref:System.Byte>、 <xref:System.Int16>、 <xref:System.Int32>、または<xref:System.Int64>列挙体のすべての値で表現できることを確認するにはCLS 準拠のプログラミング言語です。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則の違反を修正するには、サイズや互換性の問題が存在しない限り、使用<xref:System.Int32>します。 場合、<xref:System.Int32>値を保持するのに十分な大きさでない<xref:System.Int64>します。 旧バージョンとの互換性は、小さいデータ型を必要とする場合は、使用<xref:System.Byte>または<xref:System.Int16>します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

旧バージョンと互換性の問題で必要な場合にのみ、この規則による警告を抑制します。 アプリケーションでは、通常、この規則に準拠するエラーには、問題は発生しません。 ライブラリ、言語の相互運用性が必要な場合、この規則に準拠しないは、ユーザーの悪影響を及ぼす影響可能性があります。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1028.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example-of-a-violation"></a>違反の例

次の例では、推奨される基になるデータ型を使用していない 2 つの列挙体を示します。

[!code-vb[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_1.vb)]
[!code-csharp[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_1.cs)]

## <a name="example-of-how-to-fix"></a>修正する方法の例

次の例を基になるデータ型を変更することで以前の違反を修正する<xref:System.Int32>します。

[!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_2.cs)]
[!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_2.vb)]

## <a name="related-rules"></a>関連するルール

- [CA1008:列挙がゼロの値](../code-quality/ca1008-enums-should-have-zero-value.md)
- [CA1027:FlagsAttribute で列挙をマークします。](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217:FlagsAttribute で列挙をマークしないでください。](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)
- [CA1700:列挙値 'Reserved' という名前しない操作を行います](../code-quality/ca1700-do-not-name-enum-values-reserved.md)
- [CA 1712:列挙型の値を型名のプレフィックスにしません](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>関連項目

- <xref:System.Byte?displayProperty=fullName>
- <xref:System.Int16?displayProperty=fullName>
- <xref:System.Int32?displayProperty=fullName>
- <xref:System.Int64?displayProperty=fullName>
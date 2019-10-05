---
title: CA1813:アンシールド属性を使用しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1813
- AvoidUnsealedAttributes
helpviewer_keywords:
- CA1813
- AvoidUnsealedAttributes
ms.assetid: f5e31b4c-9f8b-49e1-a2a8-bb5f1140729a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 12371c34c846991a0ec41f5e9d9588c5bde8e4d6
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233597"
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813:アンシールド属性を使用しません

|||
|-|-|
|TypeName|AvoidUnsealedAttributes|
|CheckId|CA1813|
|カテゴリ|Microsoft.Performance|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

パブリック型がから<xref:System.Attribute?displayProperty=fullName>継承されており、が abstract ではなく、シールされていません (`NotInheritable` Visual Basic)。

## <a name="rule-description"></a>規則の説明

.NET には、カスタム属性を取得するためのメソッドが用意されています。 既定では、これらのメソッドで属性の継承階層が検索されます。 たとえば、は<xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> 、指定された属性の型、または指定された属性の型を拡張する任意の属性の型を検索します。 属性をシールすると、継承階層での検索が不要になり、パフォーマンスが向上します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、属性の型を封印するか、抽象にします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

このルールからの警告を抑制するのは安全です。 属性階層を定義していて、属性を封印したり、抽象にしたりすることはできません。

## <a name="example"></a>例

次の例は、この規則を満たすカスタム属性を示しています。

[!code-csharp[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/CSharp/ca1813-avoid-unsealed-attributes_1.cs)]
[!code-vb[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/VisualBasic/ca1813-avoid-unsealed-attributes_1.vb)]

## <a name="related-rules"></a>関連するルール

- [CA1019属性引数にアクセサーを定義する](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)
- [CA1018AttributeUsageAttribute で属性をマークする](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)

## <a name="see-also"></a>関連項目

- [属性](/dotnet/standard/design-guidelines/attributes)
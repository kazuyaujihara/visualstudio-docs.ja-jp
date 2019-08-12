---
title: CA2111:ポインターは参照可能にすることはできません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PointersShouldNotBeVisible
- CA2111
helpviewer_keywords:
- CA2111
- PointersShouldNotBeVisible
ms.assetid: b3a8d466-895b-43bc-a2df-5d7058fe915f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 416e45337dafd11a00e98b9adda9f16b02139f9c
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921655"
---
# <a name="ca2111-pointers-should-not-be-visible"></a>CA2111:ポインターは参照可能にすることはできません

|||
|-|-|
|TypeName|PointersShouldNotBeVisible|
|CheckId|CA2111|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
Public、protected <xref:System.IntPtr?displayProperty=fullName> 、また<xref:System.UIntPtr?displayProperty=fullName>は field は読み取り専用ではありません。

## <a name="rule-description"></a>規則の説明
 <xref:System.IntPtr>および<xref:System.UIntPtr>は、アンマネージメモリにアクセスするために使用されるポインター型です。 ポインターがプライベート、内部、または読み取り専用ではない場合、悪意のあるコードがポインターの値を変更して、メモリ内の任意の場所へのアクセスを許可したり、アプリケーションやシステムの障害を引き起こしたりする可能性があります。

ポインターフィールドを含む型へのアクセスをセキュリティで保護する場合は、 [CA2112 を参照してください。セキュリティで保護された](../code-quality/ca2112-secured-types-should-not-expose-fields.md)型はフィールドを公開しません。

## <a name="how-to-fix-violations"></a>違反の修正方法
読み取り専用、内部、またはプライベートにして、ポインターをセキュリティで保護します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
ポインターの値に依存しない場合は、このルールの警告を非表示にします。

## <a name="example"></a>例
次のコードは、規則に違反しているポインターを示しています。 非プライベートポインターもルール[CA1051 に違反していることに注意してください。参照可能なインスタンスフィールド](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)を宣言しないでください。

[!code-csharp[FxCop.Security.PointersArePrivate#1](../code-quality/codesnippet/CSharp/ca2111-pointers-should-not-be-visible_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA2112セキュリティで保護された型はフィールドを公開しません](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

[CA1051参照可能なインスタンスフィールドを宣言しない](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>関連項目

- <xref:System.IntPtr?displayProperty=fullName>
- <xref:System.UIntPtr?displayProperty=fullName>
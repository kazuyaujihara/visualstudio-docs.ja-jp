---
title: CA2235:すべてのシリアル化不可能なフィールドを設定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 886cc66f820d201b8ab7f29fee00eebce07fc176
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71238102"
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235:すべてのシリアル化不可能なフィールドを設定します

|||
|-|-|
|TypeName|MarkAllNonSerializableFields|
|CheckId|CA2235|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

シリアル化できない型のインスタンス フィールドが、シリアル化できる型で宣言されています。

## <a name="rule-description"></a>規則の説明

シリアル化可能な型は、 <xref:System.SerializableAttribute?displayProperty=fullName>属性でマークされた型です。 型をシリアル化するときに<xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> 、*シリアル化でき*ない型のインスタンスフィールドが型に含まれていて、インターフェイスを<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>実装していない場合、例外がスローされます。

> [!TIP]
> CA2235 は独自のシリアル化ロジックを提供するため<xref:System.Runtime.Serialization.ISerializable> 、を実装する型のインスタンスフィールドに対しては起動されません。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、シリアル<xref:System.NonSerializedAttribute?displayProperty=fullName>化できないフィールドに属性を適用します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

フィールドのインスタンスをシリアル化および逆シリアル<xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName>化できる型が宣言されている場合にのみ、この規則からの警告を抑制します。

## <a name="example"></a>例

次の例では、規則に違反する型と、規則を満たす2つの型を示します。

[!code-csharp[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/CSharp/ca2235-mark-all-non-serializable-fields_1.cs)]
[!code-vb[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/VisualBasic/ca2235-mark-all-non-serializable-fields_1.vb)]

## <a name="remarks"></a>コメント

Rule CA2235 は、 <xref:System.Runtime.Serialization.ISerializable>インターフェイスを実装する型 ( <xref:System.SerializableAttribute>属性でもマークされている場合を除きます) を分析しません。 これは、 [rule CA2237](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)が、 <xref:System.Runtime.Serialization.ISerializable>インターフェイスを実装する型を<xref:System.SerializableAttribute>属性と共に実装することを既に推奨しているためです。

## <a name="related-rules"></a>関連するルール

- [CA2229: シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)
- [CA2236ISerializable 型で基底クラスのメソッドを呼び出す](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)
- [CA2237:ISerializable 型を SerializableAttribute に設定します](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)
- [CA2238シリアル化メソッドを正しく実装する](../code-quality/ca2238-implement-serialization-methods-correctly.md)
- [CA2239オプションのフィールドに逆シリアル化メソッドを提供する](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)
- [CA2240ISerializable を正しく実装します](../code-quality/ca2240-implement-iserializable-correctly.md)
- [CA2120セキュリティで保護されたシリアル化コンストラクター](../code-quality/ca2120-secure-serialization-constructors.md)
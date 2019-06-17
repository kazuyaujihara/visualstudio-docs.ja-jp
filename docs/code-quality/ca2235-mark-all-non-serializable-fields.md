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
ms.openlocfilehash: 5ebfa5e9b90951acf59c8214941b93adae76d06e
ms.sourcegitcommit: 13ab9a5ab039b070b9cd9251d0b83dd216477203
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66177387"
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235:すべてのシリアル化不可能なフィールドを設定します

|||
|-|-|
|TypeName|MarkAllNonSerializableFields|
|CheckId|CA2235|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

シリアル化できない型のインスタンス フィールドが、シリアル化できる型で宣言されています。

## <a name="rule-description"></a>規則の説明

シリアル化可能な型は、いずれかでマークされている、<xref:System.SerializableAttribute?displayProperty=fullName>属性。 型がシリアル化されるとき、<xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName>型にシリアル化可能でない型のインスタンス フィールドが含まれている場合、例外がスローされます*と*を実装していない、<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>インターフェイス。

> [!TIP]
> CA2235 は発生しません。 のインスタンスを実装する型のフィールド<xref:System.Runtime.Serialization.ISerializable>、独自のシリアル化ロジックを提供するためです。

## <a name="how-to-fix-violations"></a>違反の修正方法

このルールの違反を修正するには、適用、<xref:System.NonSerializedAttribute?displayProperty=fullName>属性をシリアル化可能でないフィールド。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

場合にこの規則による警告を抑制するのみ、<xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName>シリアル化および逆シリアル化するフィールドのインスタンスを利用できる型を宣言します。

## <a name="example"></a>例

次の例では、2 つの種類: 規則と規則に適合するいずれかに違反しています。

[!code-csharp[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/CSharp/ca2235-mark-all-non-serializable-fields_1.cs)]
[!code-vb[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/VisualBasic/ca2235-mark-all-non-serializable-fields_1.vb)]

## <a name="remarks"></a>Remarks

ルールを実装する型を分析しません CA2235、<xref:System.Runtime.Serialization.ISerializable>インターフェイス (でもマークされている場合を除き、<xref:System.SerializableAttribute>属性)。 これは、ため[ca 2237 ルール](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)既にを実装する型をマークすることをお勧め、<xref:System.Runtime.Serialization.ISerializable>とのインターフェイス、<xref:System.SerializableAttribute>属性。

## <a name="related-rules"></a>関連するルール

- [CA2229: シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)
- [CA2236:ISerializable 型の基本クラス メソッドを呼び出す](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)
- [CA2237:ISerializable 型を serializableattribute に設定します](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)
- [CA2238:シリアル化メソッドを正しく実装します。](../code-quality/ca2238-implement-serialization-methods-correctly.md)
- [CA2239:オプションのフィールドに逆シリアル化メソッドを提供します。](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)
- [CA2240:ISerializable を正しく実装します。](../code-quality/ca2240-implement-iserializable-correctly.md)
- [CA2120:セキュリティで保護されたシリアル化コンス トラクター](../code-quality/ca2120-secure-serialization-constructors.md)
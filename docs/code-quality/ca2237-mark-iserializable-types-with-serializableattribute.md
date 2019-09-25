---
title: CA2237:ISerializable 型を SerializableAttribute に設定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2237
- MarkISerializableTypesWithSerializable
helpviewer_keywords:
- MarkISerializableTypesWithSerializable
- CA2237
ms.assetid: 9bd6bb24-a527-43dd-9952-043c0c694f46
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 53d049cad426201a8aaa48662061a4a424116b26
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237941"
---
# <a name="ca2237-mark-iserializable-types-with-serializableattribute"></a>CA2237:ISerializable 型を SerializableAttribute に設定します

|||
|-|-|
|TypeName|MarkISerializableTypesWithSerializable|
|CheckId|CA2237|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
外部から参照できる型が<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>インターフェイスを実装しており、型が<xref:System.SerializableAttribute?displayProperty=fullName>属性でマークされていません。 このルールは、基本型がシリアル化可能でない派生型を無視します。

## <a name="rule-description"></a>規則の説明
共通言語ランタイムによってシリアル化可能として認識されるために<xref:System.SerializableAttribute>は、型が<xref:System.Runtime.Serialization.ISerializable>インターフェイスの実装によってカスタムのシリアル化ルーチンを使用する場合でも、型は属性でマークする必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.SerializableAttribute>属性を型に適用します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
例外クラスでは、アプリケーションドメイン間で正しく機能するためにシリアル化できる必要があるため、この規則による警告を抑制しないでください。

## <a name="example"></a>例
次の例は、規則に違反する型を示しています。 規則を<xref:System.SerializableAttribute>満たすには、属性行のコメントを解除します。

[!code-vb[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/VisualBasic/ca2237-mark-iserializable-types-with-serializableattribute_1.vb)]
[!code-csharp[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/CSharp/ca2237-mark-iserializable-types-with-serializableattribute_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA2236ISerializable 型で基底クラスのメソッドを呼び出す](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

[CA2240ISerializable を正しく実装します](../code-quality/ca2240-implement-iserializable-correctly.md)

[CA2229: シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)

[CA2238シリアル化メソッドを正しく実装する](../code-quality/ca2238-implement-serialization-methods-correctly.md)

[CA2235:すべてのシリアル化不可能なフィールドを設定します](../code-quality/ca2235-mark-all-non-serializable-fields.md)

[CA2239オプションのフィールドに逆シリアル化メソッドを提供する](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

[CA2120セキュリティで保護されたシリアル化コンストラクター](../code-quality/ca2120-secure-serialization-constructors.md)
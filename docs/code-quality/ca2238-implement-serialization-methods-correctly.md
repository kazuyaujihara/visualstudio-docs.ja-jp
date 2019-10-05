---
title: CA2238:シリアル化メソッドを正しく実装します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
helpviewer_keywords:
- ImplementSerializationMethodsCorrectly
- CA2238
ms.assetid: 00882cf9-e10d-4d40-9126-3e6753e3c934
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b0bbe31f0431b259f60c1fe68a8d9edeffc572d9
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237908"
---
# <a name="ca2238-implement-serialization-methods-correctly"></a>CA2238:シリアル化メソッドを正しく実装します

|||
|-|-|
|TypeName|ImplementSerializationMethodsCorrectly|
|CheckId|CA2238|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断-メソッドがアセンブリの外部で参照可能な場合。<br /><br /> 非互換性-メソッドがアセンブリの外部で参照できない場合。|

## <a name="cause"></a>原因
シリアル化イベントを処理するメソッドに、適切なシグネチャ、戻り値の型、または参照範囲がありません。

## <a name="rule-description"></a>規則の説明
メソッドは、次のいずれかのシリアル化イベント属性を適用することによって、シリアル化イベントハンドラーとして指定されます。

- <xref:System.Runtime.Serialization.OnSerializingAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnSerializedAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnDeserializingAttribute?displayProperty=fullName>

- <xref:System.Runtime.Serialization.OnDeserializedAttribute?displayProperty=fullName>

  シリアル化イベントハンドラーは、型<xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>の1つのパラメーターを受け取り、を返し`void`、可視性を持ち`private`ます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、シリアル化イベントハンドラーの署名、戻り値の型、または可視性を修正します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、正しく宣言されたシリアル化イベントハンドラーを示しています。

[!code-vb[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/VisualBasic/ca2238-implement-serialization-methods-correctly_1.vb)]
[!code-csharp[FxCop.Usage.SerializationEventHandlers#1](../code-quality/codesnippet/CSharp/ca2238-implement-serialization-methods-correctly_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA2236ISerializable 型で基底クラスのメソッドを呼び出す](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

[CA2240ISerializable を正しく実装します](../code-quality/ca2240-implement-iserializable-correctly.md)

[CA2229: シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)

[CA2235:すべてのシリアル化不可能なフィールドを設定します](../code-quality/ca2235-mark-all-non-serializable-fields.md)

[CA2237:ISerializable 型を SerializableAttribute に設定します](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

[CA2239オプションのフィールドに逆シリアル化メソッドを提供する](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120セキュリティで保護されたシリアル化コンストラクター](../code-quality/ca2120-secure-serialization-constructors.md)
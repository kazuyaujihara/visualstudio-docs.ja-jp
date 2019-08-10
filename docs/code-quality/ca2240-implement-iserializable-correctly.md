---
title: CA2240:ISerializable を正しく実装します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2240
- ImplementISerializableCorrectly
helpviewer_keywords:
- CA2240
- ImplementISerializableCorrectly
ms.assetid: cf05936d-0d6c-49ed-a1b4-220032e50b97
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1a6d9acc3a74505f766fbf9cfe26fc6878fdbb4b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920041"
---
# <a name="ca2240-implement-iserializable-correctly"></a>CA2240:ISerializable を正しく実装します

|||
|-|-|
|TypeName|ImplementISerializableCorrectly|
|CheckId|CA2240|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

外部から参照できる型は、 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>インターフェイスに割り当てることができ、次のいずれかの条件が当てはまります。

- 型はを継承しますが、 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName>メソッドをオーバーライドしません。型は、 <xref:System.NonSerializedAttribute?displayProperty=fullName>属性でマークされていないインスタンスフィールドを宣言します。

- 型はシールされていません。 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>型は、外部から参照できないオーバーライド可能なメソッドを実装しています。

## <a name="rule-description"></a>規則の説明
インターフェイスを<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>継承する型で宣言されたインスタンスフィールドは、シリアル化プロセスに自動的に含まれません。 フィールドを含めるには、型は<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>メソッドとシリアル化コンストラクターを実装する必要があります。 フィールドをシリアル化しない場合は、フィールド<xref:System.NonSerializedAttribute>に属性を適用して明示的に決定を指定します。

シールされていない型では、 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>メソッドの実装を外部から参照できるようにする必要があります。 したがって、メソッドは派生型によって呼び出すことができ、オーバーライド可能です。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>メソッドを表示およびオーバーライドできるようにし、すべてのインスタンスフィールドがシリアル化プロセスに含まれるか、または<xref:System.NonSerializedAttribute>属性で明示的にマークされていることを確認します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、規則に違反する2つのシリアル化可能な型を示しています。

[!code-csharp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_1.cs)]
[!code-cpp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_1.cpp)]
[!code-vb[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_1.vb)]

## <a name="example"></a>例
次の例では、Book クラスにの<xref:System.Runtime.Serialization.ISerializable.GetObjectData>上書き可能な実装を提供し、ライブラリクラスにの`GetObjectData`実装を提供することによって、以前の2つの違反を修正します。

[!code-cpp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_2.cpp)]
[!code-csharp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_2.cs)]
[!code-vb[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_2.vb)]

## <a name="related-rules"></a>関連するルール

- [CA2236ISerializable 型で基底クラスのメソッドを呼び出す](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)
- [CA2229: シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)
- [CA2238シリアル化メソッドを正しく実装する](../code-quality/ca2238-implement-serialization-methods-correctly.md)
- [CA2235:すべてのシリアル化不可能なフィールドを設定します](../code-quality/ca2235-mark-all-non-serializable-fields.md)
- [CA2237:ISerializable 型を SerializableAttribute に設定します](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)
- [CA2239オプションのフィールドに逆シリアル化メソッドを提供する](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)
- [CA2120セキュリティで保護されたシリアル化コンストラクター](../code-quality/ca2120-secure-serialization-constructors.md)
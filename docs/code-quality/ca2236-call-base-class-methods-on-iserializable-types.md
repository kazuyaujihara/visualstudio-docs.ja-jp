---
title: CA2236:ISerializable 型で基底クラス メソッドを呼び出します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3f0075a6296e839030448c0209c77f1717a5fcb1
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920119"
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236:ISerializable 型で基底クラス メソッドを呼び出します

|||
|-|-|
|TypeName|CallBaseClassMethodsOnISerializableTypes|
|CheckId|CA2236|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
型は、 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>インターフェイスを実装する型から派生し、次の条件のいずれかが当てはまります。

- この型は、シリアル化コンストラクターを実装します。これは<xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>、 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>パラメーターシグネチャを持つコンストラクターですが、基本型のシリアル化コンストラクターを呼び出しません。

- 型はメソッドを<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName>実装しますが、基本<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>型のメソッドを呼び出しません。

## <a name="rule-description"></a>規則の説明
カスタムのシリアル化プロセスでは、型は<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>そのフィールドをシリアル化するメソッドと、フィールドを逆シリアル化するためのシリアル化コンストラクターを実装します。 型が<xref:System.Runtime.Serialization.ISerializable>インターフェイスを実装する型から派生している場合は、 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>基本型のフィールドをシリアル化/逆シリアル化するために、基本型のメソッドおよびシリアル化コンストラクターを呼び出す必要があります。 それ以外の場合、型はシリアル化されず、正しくシリアル化解除されません。 派生型で新しいフィールドが追加されない場合、型は<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>メソッドもシリアル化コンストラクターも実装したり、同等の基本型を呼び出したりする必要がないことに注意してください。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、対応する派生<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>型のメソッドまたはコンストラクターから基本型のメソッドまたはシリアル化コンストラクターを呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、基底クラスのシリアル化コンストラクターと<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>メソッドを呼び出すことによって、規則を満たす派生型を示しています。

[!code-vb[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/VisualBasic/ca2236-call-base-class-methods-on-iserializable-types_1.vb)]
[!code-csharp[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/CSharp/ca2236-call-base-class-methods-on-iserializable-types_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA2240ISerializable を正しく実装します](../code-quality/ca2240-implement-iserializable-correctly.md)

[CA2229: シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)

[CA2238シリアル化メソッドを正しく実装する](../code-quality/ca2238-implement-serialization-methods-correctly.md)

[CA2235:すべてのシリアル化不可能なフィールドを設定します](../code-quality/ca2235-mark-all-non-serializable-fields.md)

[CA2237:ISerializable 型を SerializableAttribute に設定します](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

[CA2239オプションのフィールドに逆シリアル化メソッドを提供する](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

[CA2120セキュリティで保護されたシリアル化コンストラクター](../code-quality/ca2120-secure-serialization-constructors.md)
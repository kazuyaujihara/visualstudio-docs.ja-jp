---
title: CA2229:シリアル化コンストラクターを実装します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dac8a9201e375877c1b586bd6415dd81764f5d2b
ms.sourcegitcommit: dae5dfd626277b58ebd7b21a75757f683f1eacc5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739232"
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229:シリアル化コンストラクターを実装します

|||
|-|-|
|TypeName|ImplementSerializationConstructors|
|CheckId|CA2229|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
この型は<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>インターフェイスを実装し、はデリゲートまたはインターフェイスではなく、次のいずれかの条件に該当します。

- 型には、オブジェクト<xref:System.Runtime.Serialization.SerializationInfo> <xref:System.Runtime.Serialization.StreamingContext>とオブジェクト (シリアル化コンストラクターのシグネチャ) を受け取るコンストラクターがありません。

- 型はシールされていません。シリアル化コンストラクターのアクセス修飾子は保護されていません (ファミリ)。

- 型が sealed で、シリアル化コンストラクターのアクセス修飾子がプライベートではありません。

## <a name="rule-description"></a>規則の説明

このルールは、カスタムシリアル化をサポートする型に関連しています。 型は、インターフェイスを<xref:System.Runtime.Serialization.ISerializable>実装する場合、カスタムシリアル化をサポートします。 シリアル化コンストラクターは、 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType>メソッドを使用してシリアル化されたオブジェクトを逆シリアル化または再作成するために必要です。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、シリアル化コンストラクターを実装します。 シールされたクラスの場合、コンストラクターをプライベートにするか、プロテクトにします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

規則違反を抑制しないでください。 この型は逆シリアル化ではなく、多くのシナリオでは機能しません。

## <a name="example"></a>例

次の例は、ルールを満たす型を示しています。

[!code-csharp[FxCop.Usage.ISerializableCtor#1](../code-quality/codesnippet/CSharp/ca2229-implement-serialization-constructors_1.cs)]

## <a name="related-rules"></a>関連するルール

[CA2237:ISerializable 型を SerializableAttribute に設定します](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>関連項目

- <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>
- <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>
- <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>

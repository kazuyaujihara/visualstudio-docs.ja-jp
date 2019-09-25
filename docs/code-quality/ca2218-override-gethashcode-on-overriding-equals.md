---
title: CA2218:オーバーライドする Equals で GetHashCode をオーバーライドします
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2218
- OverrideGetHashCodeOnOverridingEquals
helpviewer_keywords:
- OverrideGetHashCodeOnOverridingEquals
- CA2218
ms.assetid: 69b020cd-29e8-45a6-952e-32cf3ce2e21d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8699e3434dc9c4cf9d3eccc37916c20ff7f34015
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231184"
---
# <a name="ca2218-override-gethashcode-on-overriding-equals"></a>CA2218:オーバーライドする Equals で GetHashCode をオーバーライドします

|||
|-|-|
|TypeName|OverrideGetHashCodeOnOverridingEquals|
|CheckId|CA2218|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
パブリック型<xref:System.Object.Equals%2A?displayProperty=fullName>はをオーバーライドしますが<xref:System.Object.GetHashCode%2A?displayProperty=fullName>、をオーバーライドしません。

## <a name="rule-description"></a>規則の説明
 <xref:System.Object.GetHashCode%2A>現在のインスタンスに基づいて値を返します。これは、ハッシュアルゴリズムや、ハッシュテーブルなどのデータ構造に適しています。 2つのオブジェクトが同じ型で等しい場合は、次の型のインスタンスが正しく動作することを確認するために、同じハッシュコードを返す必要があります。

- <xref:System.Collections.Hashtable?displayProperty=fullName>

- <xref:System.Collections.SortedList?displayProperty=fullName>

- <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>

- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>

- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>

- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=fullName>

- <xref:System.Collections.Specialized.ListDictionary?displayProperty=fullName>

- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=fullName>

- を実装する型<xref:System.Collections.Generic.IEqualityComparer%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、の<xref:System.Object.GetHashCode%2A>実装を提供します。 同じ型のオブジェクトのペアについては、の<xref:System.Object.Equals%2A>実装がペアに対してを返す`true`場合は、実装が同じ値を返すことを確認する必要があります。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="class-example"></a>クラスの例

### <a name="description"></a>説明
次の例は、この規則に違反するクラス (参照型) を示しています。

### <a name="code"></a>コード
[!code-csharp[FxCop.Usage.GetHashCodeErrorClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_1.cs)]

### <a name="comments"></a>コメント
次の例では、をオーバーライド<xref:System.Object.GetHashCode>することによって違反を修正します。

### <a name="code"></a>コード
[!code-csharp[FxCop.Usage.GetHashCodeFixedClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_2.cs)]

## <a name="structure-example"></a>構造体の例

### <a name="description"></a>説明
次の例は、この規則に違反する構造体 (値型) を示しています。

### <a name="code"></a>コード
[!code-csharp[FxCop.Usage.GetHashCodeErrorStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_3.cs)]

### <a name="comments"></a>コメント
次の例では、をオーバーライド<xref:System.Object.GetHashCode>することによって違反を修正します。

### <a name="code"></a>コード
[!code-csharp[FxCop.Usage.GetHashCodeFixedStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_4.cs)]

## <a name="related-rules"></a>関連するルール
[CA1046参照型の演算子 equals をオーバーロードしない](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

[CA2225演算子のオーバーロードには代替の名前が付いています](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

[CA2226演算子には対称的なオーバーロードが必要です](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

[CA2224オーバーロードする演算子 equals で equals をオーバーライドします](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

[CA2231: ValueType.Equals のオーバーライドで、演算子 equals をオーバーロードします](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)

## <a name="see-also"></a>関連項目

- <xref:System.Object.Equals%2A?displayProperty=fullName>
- <xref:System.Object.GetHashCode%2A?displayProperty=fullName>
- <xref:System.Collections.Hashtable?displayProperty=fullName>
- [等値演算子](/dotnet/standard/design-guidelines/equality-operators)
---
title: CA1038:列挙子は厳密に型指定されていなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
helpviewer_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
ms.assetid: 8919f526-d487-42a4-87dc-2b2ee25260c4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56c2281f76b9064427d1d651523b9cda441eb029
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236011"
---
# <a name="ca1038-enumerators-should-be-strongly-typed"></a>CA1038:列挙子は厳密に型指定されていなければなりません

|||
|-|-|
|TypeName|EnumeratorsShouldBeStronglyTyped|
|CheckId|CA1038|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリック型またはプロテクト型<xref:System.Collections.IEnumerator?displayProperty=fullName>はを実装しますが、厳密に型<xref:System.Collections.IEnumerator.Current%2A?displayProperty=fullName>指定されたバージョンのプロパティは提供しません。 次の型から派生した型は、この規則から除外されます。

- <xref:System.Collections.CollectionBase?displayProperty=fullName>

- <xref:System.Collections.DictionaryBase?displayProperty=fullName>

- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

## <a name="rule-description"></a>規則の説明
この規則で<xref:System.Collections.IEnumerator>は、インターフェイスによって提供される機能<xref:System.Collections.IEnumerator.Current%2A>を使用するときに、ユーザーが戻り値を厳密な型にキャストする必要がないように、厳密に型指定されたバージョンのプロパティも実装する必要があります。 この規則は、を実装<xref:System.Collections.IEnumerator>する型に、よりも<xref:System.Object>強力な型のインスタンスのコレクションが含まれていることを前提としています。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、インターフェイスプロパティを明示的に実装し`IEnumerator.Current`ます (として宣言します)。 として`Current`宣言されたプロパティの、厳密に型指定されたパブリックバージョンを追加し、厳密に型指定されたオブジェクトを返すようにします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
オブジェクトベースのコレクション (バイナリツリーなど) で使用するオブジェクトベースの列挙子を実装する場合は、この規則からの警告を非表示にします。 新しいコレクションを拡張する型は、厳密に型指定された列挙子を定義し、厳密に型指定されたプロパティを公開します。

## <a name="example"></a>例
次の例は、厳密に型指定<xref:System.Collections.IEnumerator>された型を実装する正しい方法を示しています。

[!code-csharp[FxCop.Design.IEnumeratorStrongTypes#1](../code-quality/codesnippet/CSharp/ca1038-enumerators-should-be-strongly-typed_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA1035ICollection 実装は厳密に型指定されたメンバーを持つ](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)

[CA1039リストは厳密に型指定されます。](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>関連項目

- <xref:System.Collections.IEnumerator?displayProperty=fullName>
- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.DictionaryBase?displayProperty=fullName>
- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
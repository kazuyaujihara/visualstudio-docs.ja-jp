---
title: CA1035:ICollection の実装は、厳密に型指定されたメンバーを含んでいます
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ICollectionImplementationsHaveStronglyTypedMembers
- CA1035
helpviewer_keywords:
- CA1035
- ICollectionImplementationsHaveStronglyTypedMembers
ms.assetid: ad404eb5-cf6a-44b7-b78a-8ebfb654bc7f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8d9e74daa464a55a543b5eb8c189c9ddf1295301
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236026"
---
# <a name="ca1035-icollection-implementations-have-strongly-typed-members"></a>CA1035:ICollection の実装は、厳密に型指定されたメンバーを含んでいます

|||
|-|-|
|TypeName|ICollectionImplementationsHaveStronglyTypedMembers|
|CheckId|CA1035|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリック型またはプロテクト型<xref:System.Collections.ICollection?displayProperty=fullName>はを実装しますが、には<xref:System.Collections.ICollection.CopyTo%2A?displayProperty=fullName>厳密に型指定されたメソッドを提供しません。 の<xref:System.Collections.ICollection.CopyTo%2A>厳密に型指定されたバージョンは、2つ<xref:System.Array?displayProperty=fullName>のパラメーターを受け取る必要があり、最初のパラメーターとしてまたはの<xref:System.Object?displayProperty=fullName>配列を持つことはできません。

## <a name="rule-description"></a>規則の説明
この規則で<xref:System.Collections.ICollection>は、インターフェイスによって提供される機能を使用するときに、 <xref:System.Object>ユーザーが引数を型にキャストする必要がないように、厳密に型指定されたメンバーを実装する必要があります。 この規則は、を実装<xref:System.Collections.ICollection>する型が、より<xref:System.Object>強力な型のインスタンスのコレクションを管理するためにそれを行うことを前提としています。

 <xref:System.Collections.ICollection> は、<xref:System.Collections.IEnumerable?displayProperty=fullName> インターフェイスを実装します。 コレクション内のオブジェクトがを拡張<xref:System.ValueType?displayProperty=fullName>する場合は、ボックス化によって<xref:System.Collections.IEnumerable.GetEnumerator%2A>発生するパフォーマンスの低下を回避するために、厳密に型指定されたメンバーをに提供する必要があります。 コレクションのオブジェクトが参照型である場合、これは必要ありません。

インターフェイスメンバーの厳密に型指定されたバージョンを実装するには、のように、形式`InterfaceName.InterfaceMemberName` <xref:System.Collections.ICollection.CopyTo%2A>の名前を使用してインターフェイスメンバーを明示的に実装します。 明示的なインターフェイスメンバーは、インターフェイスによって宣言されたデータ型を使用します。 などのインターフェイスメンバー名<xref:System.Collections.ICollection.CopyTo%2A>を使用して、厳密に型指定されたメンバーを実装します。 厳密に型指定されたメンバーをパブリックとして宣言し、コレクションによって管理される厳密な型のパラメーターと戻り値を宣言します。 厳密な型は、インターフェイスによっ<xref:System.Object>て<xref:System.Array>宣言されているやなどの弱い型を置き換えます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、インターフェイスメンバーを明示的に実装し<xref:System.Collections.ICollection.CopyTo%2A>ます (として宣言します)。 として`CopyTo`宣言された、厳密に型指定されたパブリックメンバーを追加し、その最初のパラメーターとして厳密に型指定された配列を取得します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
バイナリツリーなどの新しいオブジェクトベースのコレクションを実装する場合、この規則からの警告を抑制します。新しいコレクションを拡張する型は、厳密な型を決定します。 これらの型は、この規則に準拠し、厳密に型指定されたメンバーを公開する必要があります。

## <a name="example"></a>例
次の例は、を実装<xref:System.Collections.ICollection>する正しい方法を示しています。

[!code-csharp[FxCop.Design.ICollectionStrongTypes#1](../code-quality/codesnippet/CSharp/ca1035-icollection-implementations-have-strongly-typed-members_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA1038列挙子は厳密に型指定する必要があります](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

[CA1039リストは厳密に型指定されます。](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>関連項目

- <xref:System.Array?displayProperty=fullName>
- <xref:System.Collections.IEnumerable?displayProperty=fullName>
- <xref:System.Collections.ICollection?displayProperty=fullName>
- <xref:System.Object?displayProperty=fullName>
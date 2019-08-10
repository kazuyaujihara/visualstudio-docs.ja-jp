---
title: CA1039:リストは厳密に型指定されています
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1039
- ListsAreStronglyTyped
helpviewer_keywords:
- CA1039
- ListsAreStronglyTyped
ms.assetid: 5ac366c4-fd87-4d5c-95d5-f755510c8e5c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 94b1e8134eb89e4ae78ec0ad6f07fd7406215185
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922839"
---
# <a name="ca1039-lists-are-strongly-typed"></a>CA1039:リストは厳密に型指定されています

|||
|-|-|
|TypeName|ListsAreStronglyTyped|
|CheckId|CA1039|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

パブリック型またはプロテクト型<xref:System.Collections.IList?displayProperty=fullName>はを実装しますが、次の1つまたは複数に対して厳密に型指定されたメソッドを提供しません。

- IList。項目

- IList. 追加

- IList. Contains

- IList. IndexOf

- IList。挿入

- IList。削除

## <a name="rule-description"></a>規則の説明

この規則で<xref:System.Collections.IList>は、インターフェイスによって提供される機能を使用するときに、 <xref:System.Object?displayProperty=fullName>ユーザーが引数を型にキャストする必要がないように、厳密に型指定されたメンバーを実装する必要があります。 インターフェイス<xref:System.Collections.IList>は、インデックスによってアクセスできるオブジェクトのコレクションによって実装されます。 この規則は、を実装<xref:System.Collections.IList>する型が、よりも<xref:System.Object>強力な型のインスタンスのコレクションを管理していることを前提としています。

<xref:System.Collections.IList><xref:System.Collections.ICollection?displayProperty=fullName>インターフェイスおよび<xref:System.Collections.IEnumerable?displayProperty=fullName>インターフェイスを実装します。 を実装<xref:System.Collections.IList>する場合は、に必要な厳密に<xref:System.Collections.ICollection>型指定されたメンバーを指定する必要があります。 コレクション内のオブジェクトがを拡張<xref:System.ValueType?displayProperty=fullName>する場合、ボックス化によって発生<xref:System.Collections.IEnumerable.GetEnumerator%2A>するパフォーマンスの低下を回避するために、に厳密に型指定されたメンバーを指定する必要があります。これは、コレクションのオブジェクトが参照型である場合には必要ありません。

この規則に準拠するには、InterfaceName の形式の名前 (など) <xref:System.Collections.IList.Add%2A>を使用して、インターフェイスメンバーを明示的に実装します。 明示的なインターフェイスメンバーは、インターフェイスによって宣言されたデータ型を使用します。 などのインターフェイスメンバー名`Add`を使用して、厳密に型指定されたメンバーを実装します。 厳密に型指定されたメンバーをパブリックとして宣言し、コレクションによって管理される厳密な型のパラメーターと戻り値を宣言します。 厳密な型は、インターフェイスによっ<xref:System.Object>て<xref:System.Array>宣言されているやなどの弱い型を置き換えます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、明示<xref:System.Collections.IList>的にメンバーを実装し、前にメモしたメンバーに対して厳密に型指定された代替手段を提供します。 <xref:System.Collections.IList>インターフェイスを正しく実装し、必要な厳密に型指定されたメンバーを提供するコードについては、次の例を参照してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
リンクリストなど、新しいオブジェクトベースのコレクションを実装する場合、この規則からの警告を抑制します。新しいコレクションを拡張する型は、厳密な型を決定します。 これらの型は、この規則に準拠し、厳密に型指定されたメンバーを公開する必要があります。

## <a name="example"></a>例
次の例では、厳密`YourType`に<xref:System.Collections.CollectionBase?displayProperty=fullName>型指定されたすべてのコレクションについて、型がを拡張しています。 <xref:System.Collections.CollectionBase><xref:System.Collections.IList>インターフェイスの明示的な実装を提供します。 したがって、と<xref:System.Collections.IList> <xref:System.Collections.ICollection>の厳密に型指定されたメンバーのみを指定する必要があります。

[!code-csharp[FxCop.Design.IListStrongTypes#1](../code-quality/codesnippet/CSharp/ca1039-lists-are-strongly-typed_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA1035ICollection 実装は厳密に型指定されたメンバーを持つ](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)

[CA1038列挙子は厳密に型指定する必要があります](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

## <a name="see-also"></a>関連項目

- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.ICollection?displayProperty=fullName>
- <xref:System.Collections.IEnumerable?displayProperty=fullName>
- <xref:System.Collections.IList?displayProperty=fullName>
- <xref:System.Object?displayProperty=fullName>
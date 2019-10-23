---
title: 'CA1039: リストは厳密に型指定されています |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1039
- ListsAreStronglyTyped
helpviewer_keywords:
- CA1039
- ListsAreStronglyTyped
ms.assetid: 5ac366c4-fd87-4d5c-95d5-f755510c8e5c
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 8845fb8bcd08f076ddc3c509a37948cf008e0623
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661803"
---
# <a name="ca1039-lists-are-strongly-typed"></a>CA1039: リストは厳密に型指定されています
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ListsAreStronglyTyped|
|CheckId|CA1039|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリック型またはプロテクト型は <xref:System.Collections.IList?displayProperty=fullName> を実装しますが、次の1つまたは複数に対して厳密に型指定されたメソッドを提供しません。

- IList。項目

- IList. 追加

- IList. Contains

- IList. IndexOf

- IList。挿入

- IList。削除

## <a name="rule-description"></a>規則の説明
 この規則では、インターフェイスによって提供される機能を使用するときに、ユーザーが引数を <xref:System.Object?displayProperty=fullName> 型にキャストする必要がないように、厳密に型指定されたメンバーを提供する <xref:System.Collections.IList> 実装が必要です。 @No__t_0 インターフェイスは、インデックスによってアクセスできるオブジェクトのコレクションによって実装されます。 この規則は、<xref:System.Collections.IList> を実装する型が、<xref:System.Object> よりも強力な型のインスタンスのコレクションを管理するためにこのように動作することを前提としています。

 <xref:System.Collections.IList> は、<xref:System.Collections.ICollection?displayProperty=fullName> および <xref:System.Collections.IEnumerable?displayProperty=fullName> インターフェイスを実装します。 @No__t_0 を実装する場合は、<xref:System.Collections.ICollection> のために必要な厳密に型指定されたメンバーを指定する必要があります。 コレクション内のオブジェクトが <xref:System.ValueType?displayProperty=fullName> を拡張する場合は、ボックス化によって発生するパフォーマンスの低下を回避するために、<xref:System.Collections.IEnumerable.GetEnumerator%2A> の厳密に型指定されたメンバーを指定する必要があります。コレクションのオブジェクトが参照型である場合、これは必要ありません。

 この規則に準拠するには、<xref:System.Collections.IList.Add%2A> のように、InterfaceMemberName という形式の名前を使用して、インターフェイスメンバーを明示的に実装します。 明示的なインターフェイスメンバーは、インターフェイスによって宣言されたデータ型を使用します。 @No__t_0 などのインターフェイスメンバー名を使用して、厳密に型指定されたメンバーを実装します。 厳密に型指定されたメンバーをパブリックとして宣言し、コレクションによって管理される厳密な型のパラメーターと戻り値を宣言します。 厳密な型は、インターフェイスによって宣言されている <xref:System.Object> や <xref:System.Array> などの弱い型を置き換えます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.Collections.IList> メンバーを明示的に実装し、前にメモしたメンバーに対して厳密に型指定された代替手段を提供します。 @No__t_0 インターフェイスを正しく実装し、必要な厳密に型指定されたメンバーを提供するコードについては、次の例を参照してください。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 リンクリストなど、新しいオブジェクトベースのコレクションを実装する場合、この規則からの警告を抑制します。新しいコレクションを拡張する型は、厳密な型を決定します。 これらの型は、この規則に準拠し、厳密に型指定されたメンバーを公開する必要があります。

## <a name="example"></a>例
 次の例では、厳密に型指定されたすべてのコレクションに対して、型 `YourType` が <xref:System.Collections.CollectionBase?displayProperty=fullName> を拡張します。 @No__t_0 には、<xref:System.Collections.IList> インターフェイスの明示的な実装が用意されていることに注意してください。 したがって、<xref:System.Collections.IList> と <xref:System.Collections.ICollection> には厳密に型指定されたメンバーのみを指定する必要があります。

 [!code-csharp[FxCop.Design.IListStrongTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.IListStrongTypes/cs/FxCop.Design.IListStrongTypes.cs#1)]

## <a name="related-rules"></a>関連規則
 [CA1035: ICollection の実装は、厳密に型指定されたメンバーを含んでいます](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)

 [CA1038: 列挙子は厳密に型指定されていなければなりません](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

## <a name="see-also"></a>参照
 <xref:System.Collections.CollectionBase?displayProperty=fullName> <xref:System.Collections.ICollection?displayProperty=fullName>
 <xref:System.Collections.IEnumerable?displayProperty=fullName>
 <xref:System.Collections.IList?displayProperty=fullName>
 <xref:System.Object?displayProperty=fullName>

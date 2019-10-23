---
title: 'CA1710: 識別子は正しいサフィックス | を持つ必要がありますMicrosoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1710
- IdentifiersShouldHaveCorrectSuffix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectSuffix
- CA1710
ms.assetid: 2b8e6dce-b4e8-4a66-ba9a-6b79be5bfe8c
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 7dc0ed72ddab39bda5f3de9b978f4d55dc2358ba
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72669169"
---
# <a name="ca1710-identifiers-should-have-correct-suffix"></a>CA1710: 識別子は、正しいサフィックスを含んでいなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|IdentifiersShouldHaveCorrectSuffix|
|CheckId|CA1710|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 識別子のサフィックスが正しくありません。

## <a name="rule-description"></a>規則の説明
 慣例として、特定の基本型を拡張する型、特定のインターフェイスを実装する型、またはこれらの型から派生した型の名前には、基本型またはインターフェイスに関連付けられたサフィックスがあります。

 名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェア ライブラリを習得するまでの時間を短縮でき、マネージド コード開発の専門家によってライブラリが開発されたという信頼を顧客に与えることができます。

 次の表に、サフィックスが関連付けられている基本型とインターフェイスの一覧を示します。

|基本型/インターフェイス|サフィックス|
|--------------------------|------------|
|<xref:System.Attribute?displayProperty=fullName>|属性|
|<xref:System.EventArgs?displayProperty=fullName>|EventArgs|
|<xref:System.Exception?displayProperty=fullName>|例外|
|<xref:System.Collections.ICollection?displayProperty=fullName>|Collection|
|<xref:System.Collections.IDictionary?displayProperty=fullName>|Dictionary|
|<xref:System.Collections.IEnumerable?displayProperty=fullName>|Collection|
|<xref:System.Collections.Queue?displayProperty=fullName>|コレクションまたはキュー|
|<xref:System.Collections.Stack?displayProperty=fullName>|コレクションまたはスタック|
|<xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>|Collection|
|<xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|Dictionary|
|<xref:System.Data.DataSet?displayProperty=fullName>|DataSet|
|<xref:System.Data.DataTable?displayProperty=fullName>|Collection または DataTable|
|<xref:System.IO.Stream?displayProperty=fullName>|ストリーム|
|<xref:System.Security.IPermission?displayProperty=fullName>|アクセス許可|
|<xref:System.Security.Policy.IMembershipCondition?displayProperty=fullName>|条件|
|イベントハンドラーデリゲート。|EventHandler|

 @No__t_0 を実装する型は、ディクショナリ、スタック、キューなどの一般化された型のデータ構造体であり、その型の使用目的に関する意味のある情報を提供する名前を使用できます。

 @No__t_0 を実装する型と、特定の項目のコレクションである型には、"Collection" という語で終わる名前があります。 たとえば、<xref:System.Collections.Queue> オブジェクトのコレクションには、' QueueCollection ' という名前が付いています。 ' Collection ' サフィックスは、`foreach` (`For Each` [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) ステートメントを使用してコレクションのメンバーを列挙できることを示します。

 型が <xref:System.Collections.IEnumerable> または <xref:System.Collections.ICollection> も実装している場合でも、<xref:System.Collections.IDictionary> を実装する型には、"Dictionary" という語で終わる名前があります。 ' Collection ' および ' Dictionary ' サフィックスの名前付け規則を使用すると、ユーザーは次の2つの列挙パターンを区別できます。

 ' Collection ' サフィックスを持つ型は、この列挙パターンに従います。

```
foreach(SomeType x in SomeCollection) { }
```

 ' Dictionary ' サフィックスを持つ型は、この列挙パターンに従います。

```
foreach(SomeType x in SomeDictionary.Values) { }
```

 @No__t_0 オブジェクトは、<xref:System.Data.DataTable> オブジェクトのコレクションで構成されます。これらのオブジェクトは、<xref:System.Data.DataColumn?displayProperty=fullName> と <xref:System.Data.DataRow?displayProperty=fullName> オブジェクトのコレクションで構成されます。 これらのコレクションは、基本 <xref:System.Data.InternalDataCollectionBase?displayProperty=fullName> クラスを使用して <xref:System.Collections.ICollection> を実装します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 型の名前を変更して、正しい語句がサフィックスとして付けられるようにします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 型が拡張される可能性がある一般化されたデータ構造であるか、または任意の多様な項目のセットを保持する場合は、' Collection ' サフィックスを使用するように警告を抑制するのが安全です。 この場合、データ構造の実装、パフォーマンス、またはその他の特性に関する意味のある情報を提供する名前が意味を持ちます (BinaryTree など)。 型が特定の型 (たとえば、StringCollection) のコレクションを表す場合、この規則からの警告を抑制しないでください。これは、`foreach` ステートメントを使用して型を列挙できることをサフィックスが示すためです。

 他のサフィックスについては、このルールからの警告を抑制しないでください。 サフィックスによって、型名から意図された使用法を明確にすることができます。

## <a name="related-rules"></a>関連規則
 [CA1711: 識別子は、不適切なサフィックスを含むことはできません](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)

## <a name="see-also"></a>参照
 [属性](https://msdn.microsoft.com/library/ee0038ef-b247-4747-a650-3c5c5cd58d8b) [NIB: イベントとデリゲート](https://msdn.microsoft.com/d98fd58b-fa4f-4598-8378-addf4355a115)

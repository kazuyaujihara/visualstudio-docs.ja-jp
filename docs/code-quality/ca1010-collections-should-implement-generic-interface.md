---
title: CA1010:コレクションは、ジェネリック インターフェイスを実装しなければなりません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
helpviewer_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 70a418b211cd4340dba9c15f0bf52e3cdfdf8e8f
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547900"
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010:コレクションは、ジェネリック インターフェイスを実装しなければなりません

|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|Category|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

型は<xref:System.Collections.IEnumerable?displayProperty=fullName>インターフェイスを実装しますが、 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>インターフェイスを実装しません。また、格納するアセンブリは .net を対象とします。 このルールは、を実装<xref:System.Collections.IDictionary?displayProperty=fullName>する型を無視します。

既定では、この規則は外部から参照できる型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

コレクションの操作性を拡充するために、ジェネリック コレクション インターフェイスの 1 つを実装します。 次に、コレクションを使用して、次のようなジェネリックコレクション型を設定できます。

- <xref:System.Collections.Generic.List%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、次のジェネリックコレクションインターフェイスのいずれかを実装します。

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>
- <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>
- <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

このルールからの警告を抑制するのは安全です。ただし、コレクションの使用には制限があります。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1010.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example-violation"></a>違反の例

次の例は、非ジェネリック`CollectionBase`クラスから派生したクラス (参照型) を示しています。このクラスは、この規則に違反します。

[!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

この規則違反を修正するには、次のいずれかの操作を行います。

- ジェネリックインターフェイスを実装します。
- 基底クラスを、ジェネリックインターフェイスと非ジェネリックインターフェイス ( `Collection<T>`クラスなど) の両方を既に実装している型に変更します。

## <a name="fix-by-base-class-change"></a>基本クラスの変更による修正

次の例では、非ジェネリック`CollectionBase`クラスからジェネリック`Collection<T>` (`Collection(Of T)` Visual Basic) クラスにコレクションの基底クラスを変更することによって、違反を修正します。

[!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

既に解放されているクラスの基底クラスの変更は、既存のコンシューマーに対する重大な変更と見なされます。

## <a name="fix-by-interface-implementation"></a>インターフェイスの実装による修正

次の例では、これらのジェネリックインターフェイスを実装`IEnumerable<T>`することに`IList<T>`よって`ICollection(Of T)`、違反`IList(Of T)`を修正します。、 `ICollection<T>`、および (`IEnumerable(Of T)`Visual Basic)。

[!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## <a name="related-rules"></a>関連するルール

- [CA1005ジェネリック型のパラメーターが多すぎないようにする](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1000ジェネリック型の静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002ジェネリックリストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006ジェネリック型をメンバーシグネチャに入れ子にしない](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004ジェネリックメソッドは型パラメーターを指定しなければなりません](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1003汎用イベントハンドラーのインスタンスを使用する](../code-quality/ca1003-use-generic-event-handler-instances.md)
- [CA1007適切な場所にジェネリックを使用する](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目

- [ジェネリック](/dotnet/csharp/programming-guide/generics/index)
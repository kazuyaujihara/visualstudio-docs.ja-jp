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
ms.openlocfilehash: c71912fdd70226e1b4be3c14be7c4e0bac26259d
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57871903"
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010:コレクションは、ジェネリック インターフェイスを実装しなければなりません

|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|Category|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

型を実装する、<xref:System.Collections.IEnumerable?displayProperty=fullName>インターフェイスしますが、実装されません、<xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>インターフェイス、および含んでいるアセンブリのターゲットの .NET です。 この規則を実装する型<xref:System.Collections.IDictionary?displayProperty=fullName>します。

既定では、このルールのみが検索に、外部から参照の種類が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

コレクションの操作性を拡充するために、ジェネリック コレクション インターフェイスの 1 つを実装します。 次などのジェネリック コレクション型を設定するコレクションを使用できます。

- <xref:System.Collections.Generic.List%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、次のジェネリック コレクション インターフェイスの 1 つを実装します。

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>
- <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>
- <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告を抑制しても安全です。ただし、コレクションの使用はより制限されます。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1010.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、[構成 FxCop アナライザー](configure-fxcop-analyzers.md)を参照してください。

## <a name="example-violation"></a>例の違反

次の例では、非ジェネリックから派生したクラス (参照型)`CollectionBase`クラスは、この規則に違反します。

[!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

この規則違反を修正するには、次のいずれかの操作を行います。

- ジェネリック インターフェイスを実装します。
- 既になど両方、ジェネリックと非ジェネリック インターフェイスを実装する型を基本クラスを変更、`Collection<T>`クラス。

## <a name="fix-by-base-class-change"></a>基本クラスの変更を修正します。

次の例から、非ジェネリック コレクションの基本クラスを変更することで、違反を修正する`CollectionBase`クラスをジェネリック`Collection<T>`(`Collection(Of T)` Visual basic) クラス。

[!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

リリース済みのクラスの基本クラスを変更すると、既存のコンシューマーに重大な変更と見なされます。

## <a name="fix-by-interface-implementation"></a>インターフェイスの実装を修正します。

次の例では、これらのジェネリック インターフェイスを実装することで、違反を修正する: `IEnumerable<T>`、 `ICollection<T>`、および`IList<T>`(`IEnumerable(Of T)`、 `ICollection(Of T)`、および`IList(Of T)`Visual Basic で)。

[!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## <a name="related-rules"></a>関連するルール

- [CA1005:ジェネリック型で過剰なパラメーターを回避します。](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA 1000:ジェネリック型で静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA 1002:ジェネリック リストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA 1006:ジェネリック型メンバー シグネチャ内で入れ子にしません](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA 1004:ジェネリック メソッドは、型パラメーターを指定する必要があります。](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA 1003:汎用イベント ハンドラーのインスタンスを使用して、](../code-quality/ca1003-use-generic-event-handler-instances.md)
- [CA 1007:適切な場所にジェネリックを使用します。](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目

- [ジェネリック](/dotnet/csharp/programming-guide/generics/index)
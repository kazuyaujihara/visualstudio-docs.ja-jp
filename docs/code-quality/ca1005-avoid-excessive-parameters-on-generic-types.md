---
title: CA1005:ジェネリック型でパラメーターを使用しすぎないでください
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ffc94a04d708315cc143afd1556cb8a2f0072e91
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923299"
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005:ジェネリック型でパラメーターを使用しすぎないでください

|||
|-|-|
|TypeName|AvoidExcessiveParametersOnGenericTypes|
|CheckId|CA1005|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
外部から参照できるジェネリック型には、3つ以上の型パラメーターがあります。

## <a name="rule-description"></a>規則の説明
ジェネリック型に含まれる型パラメーターが増えれば増えるほど、それぞれの型パラメーターが表す意味を調べることや覚えることが難しくなります。 通常、では、のよう`List<T>`に1つの型パラメーターが使用されます。また、の`Dictionary<TKey, TValue>`ように2つの型パラメーターがある場合もあります。 3つ以上の型パラメーターが存在する場合は、ほとんどのユーザーにとって困難に`TooManyTypeParameters<T, K, V>`なりC#ます`TooManyTypeParameters(Of T, K, V)` ( [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]やなど)。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、2つ以上の型パラメーターを使用するようにデザインを変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
設計に2つ以上の型パラメーターが必要な場合を除き、この規則による警告を抑制しないでください。 簡単に理解して使用できる構文でジェネリックを提供することで、新しいライブラリの導入率を習得し、向上させるために必要な時間を短縮できます。

## <a name="related-rules"></a>関連するルール
[CA1010コレクションはジェネリックインターフェイスを実装する必要があります](../code-quality/ca1010-collections-should-implement-generic-interface.md)

[CA1000ジェネリック型の静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

[CA1002ジェネリックリストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)

[CA1006ジェネリック型をメンバーシグネチャに入れ子にしない](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

[CA1004ジェネリックメソッドは型パラメーターを指定しなければなりません](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

[CA1003汎用イベントハンドラーのインスタンスを使用する](../code-quality/ca1003-use-generic-event-handler-instances.md)

[CA1007適切な場所にジェネリックを使用する](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目
[ジェネリック](/dotnet/csharp/programming-guide/generics/index)
---
title: CA1004:ジェネリック メソッドは型パラメーターを指定しなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1004
- GenericMethodsShouldProvideTypeParameter
helpviewer_keywords:
- GenericMethodsShouldProvideTypeParameter
- CA1004
ms.assetid: 38755f6a-fb45-4bf2-932e-0354ad826499
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f4c5f9c001505a76f19f2d675d552124c611f3d5
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236625"
---
# <a name="ca1004-generic-methods-should-provide-type-parameter"></a>CA1004:ジェネリック メソッドは型パラメーターを指定しなければなりません

|||
|-|-|
|TypeName|GenericMethodsShouldProvideTypeParameter|
|CheckId|CA1004|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
外部から参照できるジェネリックメソッドのパラメーターシグネチャに、メソッドのすべての型パラメーターに対応する型が含まれていません。

## <a name="rule-description"></a>規則の説明
型引数を明示的に指定するのではなく、メソッドに渡す引数の型によってジェネリック メソッドの型引数を決定する方法が推論されます。 推論を有効にするには、ジェネリック メソッドのパラメーター シグネチャに、そのメソッドの型パラメーターと同じ型のパラメーターが含まれている必要があります。 この場合、型引数を指定する必要がなくなります。 すべての型パラメーターに対して推論を使用する場合、ジェネリックおよび非ジェネリックインスタンスメソッドを呼び出すための構文は同じです。 これにより、ジェネリックメソッドの使いやすさが簡単になります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、パラメーターシグネチャにメソッドの型パラメーターごとに同じ型が含まれるようにデザインを変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。 簡単に理解して使用できる構文でジェネリックを提供することで、新しいライブラリの導入率を習得し、向上させるために必要な時間を短縮できます。

## <a name="example"></a>例
次の例は、2つのジェネリックメソッドを呼び出すための構文を示しています。 の`InferredTypeArgument`型引数は推論され、の`NotInferredTypeArgument`型引数は明示的に指定する必要があります。

[!code-vb[FxCop.Design.Inference#1](../code-quality/codesnippet/VisualBasic/ca1004-generic-methods-should-provide-type-parameter_1.vb)]
[!code-csharp[FxCop.Design.Inference#1](../code-quality/codesnippet/CSharp/ca1004-generic-methods-should-provide-type-parameter_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA1005ジェネリック型のパラメーターが多すぎないようにする](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

[CA1010コレクションはジェネリックインターフェイスを実装する必要があります](../code-quality/ca1010-collections-should-implement-generic-interface.md)

[CA1000ジェネリック型の静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

[CA1002ジェネリックリストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)

[CA1006ジェネリック型をメンバーシグネチャに入れ子にしない](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

[CA1003汎用イベントハンドラーのインスタンスを使用する](../code-quality/ca1003-use-generic-event-handler-instances.md)

[CA1007適切な場所にジェネリックを使用する](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目
[ジェネリック](/dotnet/csharp/programming-guide/generics/index)
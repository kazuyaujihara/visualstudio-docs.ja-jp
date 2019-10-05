---
title: CA1007:適切な場所にジェネリックを使用します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1007
- UseGenericsWhereAppropriate
helpviewer_keywords:
- CA1007
- UseGenericsWhereAppropriate
ms.assetid: eab780ea-3b1f-4d32-b15a-5d48da2df46b
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0d7783bea936b04fcb600563dadea6a65ac5ef5e
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236518"
---
# <a name="ca1007-use-generics-where-appropriate"></a>CA1007:適切な場所にジェネリックを使用します

|||
|-|-|
|TypeName|UseGenericsWhereAppropriate|
|CheckId|CA1007|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
外部から参照できるメソッドに型<xref:System.Object?displayProperty=fullName>の参照パラメーターが含まれており、それを含んでいるアセンブリのターゲットが 2.0 .NET Framework。

## <a name="rule-description"></a>規則の説明
参照パラメーターは、 `ref` (`ByRef` in [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) キーワードを使用して変更されたパラメーターです。 参照パラメーターに指定する引数の型は、参照パラメーターの型と正確に一致している必要があります。 参照パラメーター型から派生した型を使用するには、最初に型をキャストし、参照パラメーター型の変数に代入する必要があります。 ジェネリックメソッドを使用すると、制約の対象となるすべての型を、最初に型を参照パラメーター型にキャストせずに、メソッドに渡すことができます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、メソッドをジェネリックにして<xref:System.Object> 、型パラメーターを使用してパラメーターを置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、非ジェネリックメソッドとジェネリックメソッドの両方として実装されている汎用スワップルーチンを示しています。 ジェネリックメソッドを使用して、非ジェネリックメソッドと比較して、文字列がどの程度効率的に交換されるかに注意してください。

[!code-vb[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/VisualBasic/ca1007-use-generics-where-appropriate_1.vb)]
[!code-csharp[FxCop.Design.UseGenerics#1](../code-quality/codesnippet/CSharp/ca1007-use-generics-where-appropriate_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA1005ジェネリック型のパラメーターが多すぎないようにする](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

[CA1010コレクションはジェネリックインターフェイスを実装する必要があります](../code-quality/ca1010-collections-should-implement-generic-interface.md)

[CA1000ジェネリック型の静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

[CA1002ジェネリックリストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)

[CA1006ジェネリック型をメンバーシグネチャに入れ子にしない](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

[CA1004ジェネリックメソッドは型パラメーターを指定しなければなりません](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

[CA1003汎用イベントハンドラーのインスタンスを使用する](../code-quality/ca1003-use-generic-event-handler-instances.md)

## <a name="see-also"></a>関連項目
[ジェネリック](/dotnet/csharp/programming-guide/generics/index)
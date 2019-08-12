---
title: CA1006:ジェネリック型をメンバー シグネチャ内で入れ子にしません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotNestGenericTypesInMemberSignatures
- CA1006
helpviewer_keywords:
- CA1006
- DoNotNestGenericTypesInMemberSignatures
ms.assetid: dfc867bc-f4af-45d7-b071-db04a248f9fc
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 20bee606fd8cd98482a7304e068aaa7cbd5773a7
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923232"
---
# <a name="ca1006-do-not-nest-generic-types-in-member-signatures"></a>CA1006:ジェネリック型をメンバー シグネチャ内で入れ子にしません

|||
|-|-|
|TypeName|DoNotNestGenericTypesInMemberSignatures|
|CheckId|CA1006|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
外部から参照できるメンバーに、入れ子にされた型引数を含むシグネチャがあります。

## <a name="rule-description"></a>規則の説明
入れ子にされた型引数は、ジェネリック型の型引数でもあります。 入れ子にされた型引数を含むシグネチャを持つメンバーを呼び出すには、ユーザーが 1 つのジェネリック型をインスタンス化し、別のジェネリック型のコンストラクターにこの型を渡す必要があります。 複雑な手順と構文が必要となるため、これは避けるようにしてください。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、入れ子にされた型引数を削除するようにデザインを変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。 簡単に理解して使用できる構文でジェネリックを提供することで、新しいライブラリの導入率を習得し、向上させるために必要な時間を短縮できます。

## <a name="example"></a>例
次の例は、規則に違反するメソッドと、違反しているメソッドを呼び出すために必要な構文を示しています。

[!code-vb[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/VisualBasic/ca1006-do-not-nest-generic-types-in-member-signatures_1.vb)]
[!code-csharp[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/CSharp/ca1006-do-not-nest-generic-types-in-member-signatures_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA1005ジェネリック型のパラメーターが多すぎないようにする](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

[CA1010コレクションはジェネリックインターフェイスを実装する必要があります](../code-quality/ca1010-collections-should-implement-generic-interface.md)

[CA1000ジェネリック型の静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

[CA1002ジェネリックリストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)

[CA1004ジェネリックメソッドは型パラメーターを指定しなければなりません](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

[CA1003汎用イベントハンドラーのインスタンスを使用する](../code-quality/ca1003-use-generic-event-handler-instances.md)

[CA1007適切な場所にジェネリックを使用する](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目
[ジェネリック](/dotnet/csharp/programming-guide/generics/index)
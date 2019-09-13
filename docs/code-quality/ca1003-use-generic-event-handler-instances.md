---
title: CA1003:汎用イベント ハンドラーのインスタンスを使用します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a1ef4258d1b095395be34c7004e3f783b973897d
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547881"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003:汎用イベント ハンドラーのインスタンスを使用します

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型には、void を返し、そのシグネチャに2つのパラメーター (最初のオブジェクトと、EventArgs に割り当て可能な2つ目の型) が含まれており、それを含むアセンブリが .NET を対象とするデリゲートが含まれています。

既定では、この規則は外部から参照できる型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

.Net より前では、カスタム情報をイベントハンドラーに渡すために、 <xref:System.EventArgs?displayProperty=fullName>クラスから派生したクラスを指定した新しいデリゲートを宣言する必要がありました。 .Net では、ジェネリック<xref:System.EventHandler%601?displayProperty=fullName>デリゲートを使用して、から<xref:System.EventArgs>派生した任意のクラスをイベントハンドラーと共に使用できます。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、デリゲートを削除し、 <xref:System.EventHandler%601?displayProperty=fullName>デリゲートを使用してデリゲートを置き換えます。

デリゲートが Visual Basic コンパイラによって自動生成される場合は、 <xref:System.EventHandler%601?displayProperty=fullName>デリゲートを使用するようにイベント宣言の構文を変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1003.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example"></a>例

次の例は、規則に違反するデリゲートを示しています。 Visual Basic の例では、この例を変更してルールを満たす方法を説明しています。 C#例では、変更されたコードを表示する例を次に示します。

[!code-vb[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/VisualBasic/ca1003-use-generic-event-handler-instances_1.vb)]
[!code-csharp[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_1.cs)]

次のコードスニペットは、規則を満たす前の例からデリゲート宣言を削除します。 デリゲートを使用`ClassThatRaisesEvent` `ClassThatHandlesEvent`して、メソッドとメソッドの使用を置き換えます。 <xref:System.EventHandler%601?displayProperty=fullName>

[!code-csharp[FxCop.Design.GenericEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_2.cs)]

## <a name="related-rules"></a>関連するルール

- [CA1005ジェネリック型のパラメーターが多すぎないようにする](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1010コレクションはジェネリックインターフェイスを実装する必要があります](../code-quality/ca1010-collections-should-implement-generic-interface.md)
- [CA1000ジェネリック型の静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002ジェネリックリストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006ジェネリック型をメンバーシグネチャに入れ子にしない](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004ジェネリックメソッドは型パラメーターを指定しなければなりません](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1007適切な場所にジェネリックを使用する](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目

- [ジェネリック](/dotnet/csharp/programming-guide/generics/index)
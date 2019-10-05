---
title: CA1000:ジェネリック型の静的メンバーを宣言しません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1000
- DoNotDeclareStaticMembersOnGenericTypes
helpviewer_keywords:
- DoNotDeclareStaticMembersOnGenericTypes
- CA1000
ms.assetid: 5c0da594-f8d0-4f40-953d-56bf7fbd2087
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 4cc33c51af7d596fb9c784b76f8cc2f255ddf5a5
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236713"
---
# <a name="ca1000-do-not-declare-static-members-on-generic-types"></a>CA1000:ジェネリック型の静的メンバーを宣言しません

|||
|-|-|
|TypeName|DoNotDeclareStaticMembersOnGenericTypes|
|CheckId|CA1000|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

ジェネリック型には、 `static` (`Shared` Visual Basic) メンバーが含まれています。

既定では、この規則は外部から参照できる型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

ジェネリック型`static`のメンバーを呼び出す場合は、型に対して型引数を指定する必要があります。 推論をサポートしないジェネリック インスタンス メンバーを呼び出すときには、そのメンバーに型引数を指定する必要があります。 この2つのケースで型引数を指定する構文は、次の呼び出しで示すように、異なっていて簡単に混同できます。

```vb
' Shared method in a generic type.
GenericType(Of Integer).SharedMethod()

' Generic instance method that does not support inference.
someObject.GenericMethod(Of Integer)()
```

```csharp
// Static method in a generic type.
GenericType<int>.StaticMethod();

// Generic instance method that does not support inference.
someObject.GenericMethod<int>();
```

一般に、メンバーを呼び出すときに型引数を指定する必要がないように、前の宣言は両方とも回避する必要があります。 これにより、非ジェネリックの構文とは異なるジェネリックのメンバーを呼び出すための構文が生成されます。 詳細については[、「CA1004:ジェネリックメソッドは型パラメーター](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)を提供する必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、静的メンバーを削除するか、またはインスタンスメンバーに変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。 簡単に理解して使用できる構文でジェネリックを提供することで、新しいライブラリの導入率を習得し、向上させるために必要な時間を短縮できます。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1000.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="related-rules"></a>関連するルール

- [CA1005ジェネリック型のパラメーターが多すぎないようにする](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1010コレクションはジェネリックインターフェイスを実装する必要があります](../code-quality/ca1010-collections-should-implement-generic-interface.md)
- [CA1002ジェネリックリストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006ジェネリック型をメンバーシグネチャに入れ子にしない](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004ジェネリックメソッドは型パラメーターを指定しなければなりません](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1003汎用イベントハンドラーのインスタンスを使用する](../code-quality/ca1003-use-generic-event-handler-instances.md)
- [CA1007適切な場所にジェネリックを使用する](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目

- [ジェネリック](/dotnet/csharp/programming-guide/generics/index)
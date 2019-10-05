---
title: CA1812:インスタンス化されていない内部クラスを使用しません
ms.date: 05/16/2019
ms.topic: reference
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f924e9530a7ee43ec2222366141c3af6be2efc29
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233611"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812:インスタンス化されていない内部クラスを使用しません

|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|カテゴリ|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

内部 (アセンブリレベル) 型はインスタンス化されません。

## <a name="rule-description"></a>規則の説明

このルールは、型のいずれかのコンストラクターへの呼び出しを検索し、呼び出しが見つからない場合に違反を報告します。

この規則では、次の型は検証されません。

- 値型

- 抽象型

- 列挙

- デリゲート

- コンパイラによって生成された配列型

- インスタンス化できず、([ `Shared` Visual Basic](/dotnet/visual-basic/language-reference/modifiers/shared)) メソッド[`static`](/dotnet/csharp/language-reference/keywords/static)のみを定義する型。

を分析対象の<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName>アセンブリに適用する場合、フィールドはフレンドアセンブリによって使用される可能性が[`internal`](/dotnet/csharp/language-reference/keywords/internal)あるため、この規則は ([ `Friend` Visual Basic](/dotnet/visual-basic/language-reference/modifiers/friend)) としてマークされている型にフラグを設定しません。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、型を削除するか、この規則を使用するコードを追加します。 型にメソッドのみ`static`が含まれている場合は、次のいずれかを型に追加して、コンパイラが既定のパブリックインスタンスコンストラクターを生成しないようにします。

- .NET Framework 2.0 以降C#を対象とする型の修飾子。`static`

- .NET Framework バージョン1.0 および1.1 を対象とする型のプライベートコンストラクター。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

このルールからの警告を抑制するのは安全です。 次の状況では、この警告を非表示にすることをお勧めします。

- クラスは、などの遅延バインディングされたリフレクションメソッド<xref:System.Activator.CreateInstance%2A?displayProperty=fullName>を使用して作成されます。

- クラスは、ランタイムまたは ASP.NET によって自動的に作成されます。 自動的に作成されるクラスの例とし<xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName>て<xref:System.Web.IHttpHandler?displayProperty=fullName>、またはを実装するクラスがあります。

- クラスは、 [ `new`制約](/dotnet/csharp/language-reference/keywords/new-constraint)を持つ型パラメーターとして渡されます。 次の例は、rule CA1812 によってフラグが設定されます。

    ```csharp
    internal class MyClass
    {
        public DoSomething()
        {
        }
    }
    public class MyGeneric<T> where T : new()
    {
        public T Create()
        {
            return new T();
        }
    }

    MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
    mc.Create();
    ```

## <a name="related-rules"></a>関連するルール

- [CA1811呼び出されるプライベートコードを避ける](../code-quality/ca1811-avoid-uncalled-private-code.md)
- [CA1801使用されていないパラメーターの確認](../code-quality/ca1801-review-unused-parameters.md)
- [CA1804未使用のローカルの削除](../code-quality/ca1804-remove-unused-locals.md)
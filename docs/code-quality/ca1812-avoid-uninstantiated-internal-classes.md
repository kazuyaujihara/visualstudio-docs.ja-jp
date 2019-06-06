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
ms.openlocfilehash: a0d55af3c5522c6bb9aa3ad8a023f070c187ca6f
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714269"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812:インスタンス化されていない内部クラスを使用しません

|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|カテゴリ|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

内部 (アセンブリ レベル) 型がインスタンス化されることはありません。

## <a name="rule-description"></a>規則の説明

このルールは、型のコンス トラクターの 1 つの呼び出しを検索しようし、呼び出しが検出されない場合は、違反を報告します。

次の種類は、このルールではチェックされません。

- 値型

- 抽象型

- 列挙

- デリゲート

- コンパイラによって生成された配列型

- 型をインスタンス化することはできず、のみを定義する[ `static` ](/dotnet/csharp/language-reference/keywords/static) ([ `Shared` Visual Basic で](/dotnet/visual-basic/language-reference/modifiers/shared)) メソッドです。

適用する場合、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName>は分析されて、アセンブリをこの規則はフラグは設定されませんとしてマークされている型[ `internal` ](/dotnet/csharp/language-reference/keywords/internal) ([ `Friend` Visual Basic で](/dotnet/visual-basic/language-reference/modifiers/friend)) フィールドを指定することがありますので、フレンド アセンブリによって使用されます。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、型を削除するか、それを使用するコードを追加します。 型にのみ含まれる場合`static`をコンパイラが既定のパブリック インスタンス コンス トラクターを生成するを防ぐために型に、次のいずれかのメソッドを追加します。

- `static`の修飾子C#型を対象とする[!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]またはそれ以降。

- .NET Framework version 1.0 および 1.1 を対象とする型のプライベート コンス トラクターです。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

このルールから警告を抑制しても安全です。 次の状況では、この警告を抑制することをお勧めします。

- などクラスが遅延バインディング リフレクション メソッドによって作成された<xref:System.Activator.CreateInstance%2A?displayProperty=fullName>します。

- クラスは、ランタイムまたは ASP.NET によって自動的に作成されます。 自動的に作成されたクラスの例をいくつかは実装される<xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName>または<xref:System.Web.IHttpHandler?displayProperty=fullName>します。

- クラスは、型のパラメーターとして渡される、 [ `new`制約](/dotnet/csharp/language-reference/keywords/new-constraint)します。 次の例は、CA1812 ルールによってフラグが設定されます。

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

- [CA1811:呼び出されていないプライベート コードを避ける](../code-quality/ca1811-avoid-uncalled-private-code.md)
- [CA 1801:未使用のパラメーターをレビューします](../code-quality/ca1801-review-unused-parameters.md)
- [CA 1804:使用されていないローカルを削除します](../code-quality/ca1804-remove-unused-locals.md)
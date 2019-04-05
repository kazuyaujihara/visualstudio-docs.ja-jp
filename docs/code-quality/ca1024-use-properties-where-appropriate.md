---
title: CA1024:適切な場所にプロパティを使用します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UsePropertiesWhereAppropriate
- CA1024
helpviewer_keywords:
- CA1024
- UsePropertiesWhereAppropriate
ms.assetid: 3a04f765-af7c-4872-87ad-9cc29e8e657f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e4008872a7cb96386ef702d21ba8a18d96037d83
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57869258"
---
# <a name="ca1024-use-properties-where-appropriate"></a>CA1024:適切な場所にプロパティを使用します

|||
|-|-|
|TypeName|UsePropertiesWhereAppropriate|
|CheckId|CA1024|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

メソッドの名前で始まる名前が`Get`パラメーターは、配列でない値を返します。

既定では、このルールだけが検索でパブリックおよびプロテクト メソッドが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

ほとんどの場合、プロパティは、データを表すし、メソッドがアクションを実行します。 プロパティは、それらを使いやすく、フィールドのようにアクセスします。 メソッドは、これらの条件のいずれかが存在する場合、プロパティに適した候補です。

- 引数を受け取らないし、オブジェクトの状態情報を返します。

- オブジェクトの状態の一部を設定する 1 つの引数を受け取ります。

プロパティがフィールドが表示されるかのように動作する必要があります。メソッドには、することはできません。 プロパティを変更しない必要があります。 メソッドは、次の状況でのプロパティよりも優れています。

- メソッドは、時間のかかる操作を実行します。 メソッドでは、フィールドの値を取得または設定するために必要な時間よりも明らかに長くかかります。

- メソッドは、変換を実行します。 フィールドへのアクセス、保存されるデータの変換後のバージョンは返されません。

- Get メソッドでは、監視可能な副作用が発生します。 フィールドの値を取得する場合は、副作用は生成されません。

- 実行の順序が重要です。 フィールドの値の設定は、その他の操作が発生するときに依存しません。

- 連続して 2 回のメソッドを呼び出すには、異なる結果が作成されます。

- メソッドは静的だが、呼び出し元によって変更可能なオブジェクトを返します。 フィールドの値を取得するフィールドが格納されているデータを変更する呼び出し元を許可しません。

- メソッドでは、配列を返します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を解決するには、プロパティに、メソッドを変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

メソッドが上記の条件の少なくとも 1 つを満たしている場合は、この規則による警告を抑制します。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1024.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、[構成 FxCop アナライザー](configure-fxcop-analyzers.md)を参照してください。

## <a name="control-property-expansion-in-the-debugger"></a>デバッガーでのコントロール プロパティの展開

プログラマは、プロパティを使用を避ける理由の 1 つは、デバッガーをしないためですが。 たとえば、大きなオブジェクトの割り当てや、P/invoke を呼び出し、プロパティを伴う可能性が観測可能な副作用が実際に必要がありますいません。

Autoexpanding プロパティからデバッガーを適用することで回避できます<xref:System.Diagnostics.DebuggerBrowsableAttribute?displayProperty=fullName>します。 次の例では、インスタンス プロパティに適用されているこの属性を示します。

```vb
Imports System
Imports System.Diagnostics

Namespace Microsoft.Samples

    Public Class TestClass

        ' [...]

        <DebuggerBrowsable(DebuggerBrowsableState.Never)> _
        Public ReadOnly Property LargeObject() As LargeObject
            Get
                ' Allocate large object
                ' [...]
            End Get
        End Property

    End Class

End Namespace
```

```csharp
using System;
using System.Diagnostics;

namespace Microsoft.Samples
{
    publicclass TestClass
    {
        // [...]

        [DebuggerBrowsable(DebuggerBrowsableState.Never)]
        public LargeObject LargeObject
        {
            get
            {
                // Allocate large object
                // [...]
            }
        }
    }
}
```

## <a name="example"></a>例

次の例では、いくつかのメソッドをプロパティに変換する必要があり、フィールドのように動作しないためではなく必要がありますをいくつか含まれています。

[!code-csharp[FxCop.Design.MethodsProperties#1](../code-quality/codesnippet/CSharp/ca1024-use-properties-where-appropriate_1.cs)]
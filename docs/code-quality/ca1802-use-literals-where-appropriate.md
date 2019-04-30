---
title: CA1802:適切な場所にリテラルを使用します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f4dbafb4c6f7ad590244842ac3def0e26f8a14fd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62797068"
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802:適切な場所にリテラルを使用します

|||
|-|-|
|TypeName|UseLiteralsWhereAppropriate|
|CheckId|CA1802|
|Category|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

フィールドが宣言されている`static`と`readonly`(`Shared`と`ReadOnly`Visual Basic で)、およびコンパイル時に計算される値で初期化されます。

既定では、このルールだけを確認、外部から参照できるフィールドが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

値を`static readonly`フィールドは、宣言型の静的コンス トラクターが呼び出されたときに実行時に計算されます。 場合、`static readonly`フィールドは宣言されているし、静的コンス トラクターが明示的に宣言しないコンパイラは、フィールドを初期化するために静的コンス トラクターを生成するときに初期化されます。

値を`const`フィールドがコンパイル時に計算し、と比較した場合、実行時のパフォーマンスを向上すると、メタデータに格納されている、`static readonly`フィールド。

対象フィールドに割り当てられた値は、コンパイル時に計算、ために宣言を変更、`const`フィールド値は実行時ではなく、コンパイル時に計算されます。

## <a name="how-to-fix-violations"></a>違反の修正方法

このルールの違反を修正するには、置換、`static`と`readonly`修飾子を`const`修飾子。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

パフォーマンスが重大な問題がない場合、この規則による警告を抑制またはルールを無効にも安全です。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1802.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (パフォーマンス) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example"></a>例

次の例は、型`UseReadOnly`、ルールと、型に違反する`UseConstant`ルールを満たします。

[!code-vb[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/VisualBasic/ca1802-use-literals-where-appropriate_1.vb)]
[!code-csharp[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/CSharp/ca1802-use-literals-where-appropriate_1.cs)]
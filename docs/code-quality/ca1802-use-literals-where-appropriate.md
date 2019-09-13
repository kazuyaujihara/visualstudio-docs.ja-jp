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
ms.openlocfilehash: c6512f02d13c2eeb441f5b374c4785deffe22a22
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547066"
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802:適切な場所にリテラルを使用します

|||
|-|-|
|TypeName|UseLiteralsWhereAppropriate|
|CheckId|CA1802|
|Category|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

フィールドは、( `static` `readonly` `Shared` および`ReadOnly` Visual Basic) として宣言され、コンパイル時に計算できるという値で初期化されます。

既定では、この規則は外部から参照できるフィールドのみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

`static readonly`フィールドの値は、宣言する型の静的コンストラクターが呼び出されるときに、実行時に計算されます。 `static readonly`フィールドが宣言時に初期化され、静的コンストラクターが明示的に宣言されていない場合、コンパイラは静的コンストラクターを生成してフィールドを初期化します。

`const`フィールドの値はコンパイル時に計算され、メタデータに格納されます。これにより、 `static readonly`フィールドと比較したときの実行時のパフォーマンスが向上します。

コンパイル時には対象のフィールドに割り当てられた値が計算できるであるため、 `const`宣言をフィールドに変更して、実行時ではなくコンパイル時に値が計算されるようにします。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、 `static` `const`修飾子と`readonly`修飾子を修飾子で置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

このルールからの警告を抑制することも、パフォーマンスが問題にならない場合はルールを無効にすることも安全です。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1802.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (パフォーマンス) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example"></a>例

次の例は、規則に`UseReadOnly`違反する型と、規則に適合する`UseConstant`型 () を示しています。

[!code-vb[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/VisualBasic/ca1802-use-literals-where-appropriate_1.vb)]
[!code-csharp[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/CSharp/ca1802-use-literals-where-appropriate_1.cs)]
---
title: CA2230:可変引数に対して param を使用します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0639d30771b3a6bb288ddbf9644dda2efcd5f90d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231358"
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230:可変引数に対して param を使用します

|||
|-|-|
|TypeName|UseParamsForVariableArguments|
|CheckId|CA2230|
|Category|Microsoft.Usage|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリックまたはプロテクト型に、 `VarArgs`呼び出し規約を使用するパブリックメソッドまたはプロテクトメソッドが含まれています。

## <a name="rule-description"></a>規則の説明
呼び出し`VarArgs`規約は、可変個のパラメーターを受け取る特定のメソッド定義で使用されます。 `VarArgs`呼び出し規約を使用するメソッドは、共通言語仕様 (CLS) に準拠していないため、プログラミング言語間でアクセスできない可能性があります。

でC#は、 `VarArgs`メソッドのパラメーター `__arglist`リストがキーワードで終了するときに、呼び出し規約が使用されます。 Visual Basic は`VarArgs`呼び出し規約をサポートしていませC++ん。ビジュアルでは、楕円`...`表記法を使用するアンマネージコードでのみ使用できます。

## <a name="how-to-fix-violations"></a>違反の修正方法
でC#のこの規則違反を修正するには、`__arglist` の代わりに [params](/dotnet/csharp/language-reference/keywords/params) キーワードを使用します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、2つのメソッドを示しています。1つは規則に違反し、もう1つは規則を満たしています。

[!code-csharp[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]

## <a name="see-also"></a>関連項目

- <xref:System.Reflection.CallingConventions?displayProperty=fullName>
- [言語への非依存性、および言語非依存コンポーネント](/dotnet/standard/language-independence-and-language-independent-components)
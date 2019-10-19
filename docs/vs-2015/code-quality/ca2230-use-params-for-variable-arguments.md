---
title: 'CA2230: 可変個の引数に対して params を使用します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: a690544a7ed03094587a2aaf1c44b7ed68e8f2a9
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662824"
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: 可変引数に対して param を使用します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseParamsForVariableArguments|
|CheckId|CA2230|
|カテゴリ|Microsoft. 使用方法|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリックまたはプロテクト型に、`VarArgs` の呼び出し規約を使用するパブリックメソッドまたはプロテクトメソッドが含まれています。

## <a name="rule-description"></a>規則の説明
 @No__t_0 呼び出し規約は、可変個のパラメーターを受け取る特定のメソッド定義で使用されます。 @No__t_0 の呼び出し規約を使用するメソッドは、共通言語仕様 (CLS) に準拠していないため、プログラミング言語間でアクセスできない可能性があります。

 でC#は、メソッドのパラメーターリストが `__arglist` キーワードで終了するときに、`VarArgs` 呼び出し規約が使用されます。 Visual Basic は `VarArgs` 呼び出し規約をサポートしていませC++ん。ビジュアルでは、楕円 `...` 表記を使用するアンマネージコードでのみ使用できます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 でC#のこの規則違反を修正するには、`__arglist` ではなく[params](https://msdn.microsoft.com/library/1690815e-b52b-4967-8380-5780aff08012)キーワードを使用します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例は、2つのメソッドを示しています。1つは規則に違反し、もう1つは規則を満たしています。

 [!code-csharp[FxCop.Usage.UseParams#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.UseParams/cs/FxCop.Usage.UseParams.cs#1)]

## <a name="see-also"></a>参照
 [言語への非依存性と言語に依存しないコンポーネントの](https://msdn.microsoft.com/library/4f0b77d0-4844-464f-af73-6e06bedeafc6)<xref:System.Reflection.CallingConventions?displayProperty=fullName>

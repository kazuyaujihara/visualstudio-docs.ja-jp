---
title: 'CA2241: 書式設定メソッドに正しい引数を指定してください |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2241
- Provide correct arguments to formatting methods
- ProvideCorrectArgumentsToFormattingMethods
helpviewer_keywords:
- ProvideCorrectArgumentsToFormattingMethods
- CA2241
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 112065b2a8b9a88241ce62dda7b32a2f2c22fc75
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672029"
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241: 正しい引数を書式指定メソッドに指定します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ProvideCorrectArgumentsToFormattingMethods|
|CheckId|CA2241|
|カテゴリ|Microsoft. 使用方法|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 @No__t_1、<xref:System.Console.Write%2A>、<xref:System.String.Format%2A?displayProperty=fullName> などのメソッドに渡された `format` 文字列引数に、各オブジェクト引数に対応する書式指定項目が含まれていません。また、その逆も同様です。

## <a name="rule-description"></a>規則の説明
 @No__t_0、<xref:System.Console.Write%2A>、<xref:System.String.Format%2A> などのメソッドの引数は、書式指定文字列の後に複数の <xref:System.Object?displayProperty=fullName> インスタンスが続く形式で構成されます。 書式指定文字列は、{index [, alignment] [: formatString]} という形式のテキストと埋め込み書式項目で構成されます。 ' index ' は、どのオブジェクトを書式設定するかを示す、0から始まる整数です。 オブジェクトの書式指定文字列に対応するインデックスがない場合、オブジェクトは無視されます。 ' Index ' によって指定されたオブジェクトが存在しない場合は、実行時に <xref:System.FormatException?displayProperty=fullName> がスローされます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、各オブジェクト引数に書式項目を指定し、各書式指定項目にオブジェクト引数を指定します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例は、規則の2つの違反を示しています。

 [!code-csharp[FxCop.Usage.FormattingArguments#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.FormattingArguments/cs/FxCop.Usage.FormattingArguments.cs#1)]
 [!code-vb[FxCop.Usage.FormattingArguments#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.FormattingArguments/vb/FxCop.Usage.FormattingArguments.vb#1)]

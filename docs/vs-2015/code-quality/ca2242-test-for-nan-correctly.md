---
title: 'CA2242: NaN に対して正しくテストします |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 8433ac081a45e3dbab80ffcd6f96e6d1db914337
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672005"
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242: NaN に対して正しくテストします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TestForNaNCorrectly|
|CheckId|CA2242|
|カテゴリ|Microsoft. 使用方法|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 式は <xref:System.Single.NaN?displayProperty=fullName> または <xref:System.Double.NaN?displayProperty=fullName> に対して値をテストします。

## <a name="rule-description"></a>規則の説明
 <xref:System.Double.NaN?displayProperty=fullName> (非数) を表し、算術演算が未定義の場合に結果が返されます。 値と <xref:System.Double.NaN?displayProperty=fullName> が等しいかどうかをテストする式は、常に `false` を返します。 値と <xref:System.Double.NaN?displayProperty=fullName> の等しくないかどうかをテストする式は、常に `true` を返します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則の違反を修正し、値が <xref:System.Double.NaN?displayProperty=fullName> を表すかどうかを正確に判断するには、<xref:System.Single.IsNaN%2A?displayProperty=fullName> または <xref:System.Double.IsNaN%2A?displayProperty=fullName> を使用して値をテストします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、<xref:System.Double.NaN?displayProperty=fullName> に対して誤って値をテストする2つの式と、値をテストするために <xref:System.Double.IsNaN%2A?displayProperty=fullName> を正しく使用する式を示します。

 [!code-csharp[FxCop.Usage.TestForNaN#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.TestForNaN/cs/FxCop.Usage.TestForNaN.cs#1)]
 [!code-vb[FxCop.Usage.TestForNaN#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.TestForNaN/vb/FxCop.Usage.TestForNaN.vb#1)]

---
title: CA2242:NaN に対して正しくテストします
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8912cb6eeec8009364936a42d572f4f3d83fae5e
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919917"
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242:NaN に対して正しくテストします

|||
|-|-|
|TypeName|TestForNaNCorrectly|
|CheckId|CA2242|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
式は、または<xref:System.Single.NaN?displayProperty=fullName> <xref:System.Double.NaN?displayProperty=fullName>に対して値をテストします。

## <a name="rule-description"></a>規則の説明
 <xref:System.Double.NaN?displayProperty=fullName>は、算術演算が定義されていない場合に、数値以外の結果を表します。 値の間の等価性をテストし<xref:System.Double.NaN?displayProperty=fullName> 、常`false`にを返す式。 値が等しくないかどうかをテスト<xref:System.Double.NaN?displayProperty=fullName>し、 `true`常にを返す式。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正し、値がを表す<xref:System.Double.NaN?displayProperty=fullName>かどうかを正確に判断するには、または<xref:System.Double.IsNaN%2A?displayProperty=fullName>を使用<xref:System.Single.IsNaN%2A?displayProperty=fullName>して値をテストします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例では、値を<xref:System.Double.NaN?displayProperty=fullName>誤ってテストする2つの式と、値をテストするために正しく使用<xref:System.Double.IsNaN%2A?displayProperty=fullName>する式を示します。

[!code-vb[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/VisualBasic/ca2242-test-for-nan-correctly_1.vb)]
[!code-csharp[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/CSharp/ca2242-test-for-nan-correctly_1.cs)]
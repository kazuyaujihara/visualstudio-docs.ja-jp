---
title: CA2130:セキュリティ上重要な定数は透過的である必要がある
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 62cf9b6b62dac85251d9fca434b35f0a7c6254c7
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232421"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130:セキュリティ上重要な定数は透過的である必要がある

|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
定数フィールドまたは列挙型のメンバーは、 <xref:System.Security.SecurityCriticalAttribute>でマークされます。

## <a name="rule-description"></a>規則の説明
実行時に検索の必要がない値がコンパイラのインライン定数に設定されているため、定数値に対して透過性は適用されません。 透過的なコードからは定数にアクセスできないとコード レビューアーが考えることがないよう、定数フィールドは透過的セキュリティなフィールドとして定義する必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、フィールドまたは値から SecurityCritical 属性を削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例では、列挙値`EnumWithCriticalValues.CriticalEnumValue`と定数`CriticalConstant`によってこの警告が発生します。 問題を解決するには、[`SecurityCritical`] 属性を削除して、セキュリティを透過的にします。

[!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]
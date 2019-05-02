---
title: CA2146:型は、基本型およびインターフェイスと同程度以上、重要でなければならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2146
ms.assetid: 241fb784-1f6b-46e5-8ceb-c438e341d38e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 01a8a5609394f0dd428066e32fb425a2abb486c4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62542054"
---
# <a name="ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces"></a>CA2146:型は、基本型およびインターフェイスと同程度以上、重要でなければならない

|||
|-|-|
|TypeName|TypesMustBeAtLeastAsCriticalAsBaseTypes|
|CheckId|CA2146|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 透過的な型はでマークされている型から派生、<xref:System.Security.SecuritySafeCriticalAttribute>または<xref:System.Security.SecurityCriticalAttribute>、またはでマークされている型、<xref:System.Security.SecuritySafeCriticalAttribute>属性でマークされている型から派生、<xref:System.Security.SecurityCriticalAttribute>属性。

## <a name="rule-description"></a>規則の説明
 派生型に透過的セキュリティ属性が設定されていて、この属性が基本型または実装されたインターフェイスほど重要ではない場合に、この規則が適用されます。 クリティカルな基本型から派生したり、クリティカルなインターフェイスを実装したりできるのは、クリティカルなデータ型だけです。また、セーフ クリティカルな基本型から派生したり、セーフ クリティカルなインターフェイスを実装したりできるのは、クリティカルまたはセーフ クリティカルなデータ型だけです。 レベル 2 の透過性では、この規則の違反が発生する、<xref:System.TypeLoadException>の派生型。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この違反を修正するには、少なくともほど重要では、基本型またはインターフェイスの透過性属性を持つ派生または実装する型をマークします。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 [!code-csharp[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../code-quality/codesnippet/CSharp/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces_1.cs)]
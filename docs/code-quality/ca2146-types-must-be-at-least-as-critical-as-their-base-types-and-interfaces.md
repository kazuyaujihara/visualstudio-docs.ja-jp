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
ms.openlocfilehash: ce7870077cb859a25de70c726c78cad1d50270e5
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231941"
---
# <a name="ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces"></a>CA2146:型は、基本型およびインターフェイスと同程度以上、重要でなければならない

|||
|-|-|
|TypeName|TypesMustBeAtLeastAsCriticalAsBaseTypes|
|CheckId|CA2146|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
<xref:System.Security.SecuritySafeCriticalAttribute>透過型は、 <xref:System.Security.SecurityCriticalAttribute>またはでマークされた型から派生します。または、 <xref:System.Security.SecuritySafeCriticalAttribute>属性でマークされた型は、 <xref:System.Security.SecurityCriticalAttribute>属性でマークされた型から派生します。

## <a name="rule-description"></a>規則の説明
派生型に透過的セキュリティ属性が設定されていて、この属性が基本型または実装されたインターフェイスほど重要ではない場合に、この規則が適用されます。 クリティカルな基本型から派生したり、クリティカルなインターフェイスを実装したりできるのは、クリティカルなデータ型だけです。また、セーフ クリティカルな基本型から派生したり、セーフ クリティカルなインターフェイスを実装したりできるのは、クリティカルまたはセーフ クリティカルなデータ型だけです。 レベル2の透過性でこの規則を違反すると<xref:System.TypeLoadException> 、派生型のがになります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この違反を修正するには、基本型またはインターフェイスとして少なくとも重要な透過性属性を使用して、派生または実装する型をマークします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
[!code-csharp[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../code-quality/codesnippet/CSharp/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces_1.cs)]
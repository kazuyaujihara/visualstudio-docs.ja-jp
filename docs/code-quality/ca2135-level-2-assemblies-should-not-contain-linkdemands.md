---
title: CA2135:レベル 2 のアセンブリは LinkDemand を含んではならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d466a508eade835563627a829f937416a24972a0
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920647"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135:レベル 2 のアセンブリは LinkDemand を含んではならない

|||
|-|-|
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
クラスまたはクラスメンバーが、 <xref:System.Security.Permissions.SecurityAction>レベル2のセキュリティを使用しているアプリケーションでを使用しています。

## <a name="rule-description"></a>規則の説明
LinkDemands は、レベル 2 のセキュリティ規則セットでは使用が非推奨とされます。 Linkdemand を使用して just-in-time (JIT) コンパイル時にセキュリティを適用するのではなく、メソッド、型、およびフィールドを<xref:System.Security.SecurityCriticalAttribute>属性でマークします。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、を<xref:System.Security.Permissions.SecurityAction>削除し、 <xref:System.Security.SecurityCriticalAttribute>属性を使用して型またはメンバーをマークします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例では、 <xref:System.Security.Permissions.SecurityAction>を削除し、メソッドを<xref:System.Security.SecurityCriticalAttribute>属性でマークします。

[!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2135-level-2-assemblies-should-not-contain-linkdemands_1.cs)]
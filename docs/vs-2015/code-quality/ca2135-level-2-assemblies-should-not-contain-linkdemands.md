---
title: 'CA2135: レベル2のアセンブリは Linkdemand | を含むことはできませんMicrosoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 1248ac41a757ba2fc26ef0659c0f93ee325bc605
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72602943"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: レベル 2 のアセンブリは LinkDemand を含んではならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 クラスまたはクラスメンバーが、レベル2のセキュリティを使用しているアプリケーションで <xref:System.Security.Permissions.SecurityAction> を使用しています。

## <a name="rule-description"></a>規則の説明
 LinkDemands は、レベル 2 のセキュリティ規則セットでは使用が非推奨とされます。 Linkdemand を使用してジャストインタイム (JIT) コンパイル時にセキュリティを適用するのではなく、メソッド、型、およびフィールドを <xref:System.Security.SecurityCriticalAttribute> 属性でマークします。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.Security.Permissions.SecurityAction> を削除し、型またはメンバーを <xref:System.Security.SecurityCriticalAttribute> 属性でマークします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、<xref:System.Security.Permissions.SecurityAction> を削除し、メソッドを <xref:System.Security.SecurityCriticalAttribute> 属性でマークします。

 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2135.securityrulesetlevel2methodsshouldnotbeprotectedwithlinkdemands/cs/ca2135.cs#1)]

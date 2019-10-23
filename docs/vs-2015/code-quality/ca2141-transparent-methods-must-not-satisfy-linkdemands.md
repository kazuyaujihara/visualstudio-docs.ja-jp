---
title: 'CA2141: Transparent メソッドは Linkdemand | を満たすことはできません。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 5e8e88401a6fbe3ab7dc635dadee9215b049b2d5
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72602839"
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141: 透過的メソッドは、LinkDemand を満たしてはならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 透過的セキュリティメソッドは、<xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 属性でマークされていないアセンブリ内のメソッドを呼び出します。また、透過的セキュリティメソッドは、型またはメソッドに対して <xref:System.Security.Permissions.SecurityAction> `.LinkDemand` を満たします。

## <a name="rule-description"></a>規則の説明
 LinkDemand を満たすことは、セキュリティ上重要な操作であり、意図しない特権の昇格を引き起こす可能性があります。 透過的セキュリティコードは、セキュリティクリティカルなコードと同じセキュリティ監査要件の対象にならないため、Linkdemand を満たしてはなりません。 セキュリティ規則セットレベル1のアセンブリの透過的メソッドによって、対応するすべての Linkdemand が実行時に完全な要求に変換され、パフォーマンスの問題が発生する可能性があります。 セキュリティ規則セットレベル2のアセンブリでは、LinkDemand を満たす場合、transparent メソッドはジャストインタイム (JIT) コンパイラでのコンパイルに失敗します。

 E レベル2のセキュリティを使っているアセンブリでは、セキュリティ transparent メソッドによって LinkDemand を満たすか、非 APTCA アセンブリのメソッドを呼び出すと、<xref:System.MethodAccessException> が発生します。レベル1のアセンブリでは、LinkDemand は完全な要求になります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、アクセスメソッドを <xref:System.Security.SecurityCriticalAttribute> または <xref:System.Security.SecuritySafeCriticalAttribute> 属性でマークするか、アクセスされたメソッドから LinkDemand を削除します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 この例では、transparent メソッドは LinkDemand を持つメソッドを呼び出そうとします。 このルールは、このコードで発生します。

 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2141.transparentmethodsmustnotsatisfylinkdemands/cs/ca2141 - transparentmethodsmustnotsatisfylinkdemands.cs#1)]

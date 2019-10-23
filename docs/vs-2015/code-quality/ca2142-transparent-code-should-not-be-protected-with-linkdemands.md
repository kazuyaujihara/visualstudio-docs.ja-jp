---
title: 'CA2142: Transparent code を Linkdemand | で保護することはできませんMicrosoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: a9d8986e9d1e6fc3f614e23fff3f6a24c1cc6e91
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72602775"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: 透過的コードは、LinkDemand を使用して保護されてはならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 透過的な方法では、<xref:System.Security.Permissions.SecurityAction> またはその他のセキュリティ要求が必要です。

## <a name="rule-description"></a>規則の説明
 この規則は、アクセスするために LinkDemands を要求する透過的メソッドに対して適用されます。 透過的セキュリティ コードでは、操作のセキュリティ検証を行うことができないため、アクセス許可を要求できません。 透過的な方法はセキュリティに中立的であると想定されているため、セキュリティ上の決定を行うべきではありません。 また、セキュリティ上の決定を行うセーフクリティカルコードは、以前にこのような決定を行った透過的なコードに依存しないようにする必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則の違反を修正するには、transparent メソッドに対するリンク確認要求を削除するか、セキュリティ要求などのセキュリティチェックを実行する場合は、<xref:System.Security.SecuritySafeCriticalAttribute> 属性を使用してメソッドをマークします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、メソッドに対してルールが適用されます。これは、メソッドが透過的で、<xref:System.Security.Permissions.SecurityAction> を含む LinkDemand <xref:System.Security.PermissionSet> でマークされているためです。

 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2142.transparentmethodsshouldnotbeprotectedwithlinkdemands/cs/ca2142 -transparentmethodsshouldnotbeprotectedwithlinkdemands.cs#1)]

 この規則による警告は抑制しないでください。

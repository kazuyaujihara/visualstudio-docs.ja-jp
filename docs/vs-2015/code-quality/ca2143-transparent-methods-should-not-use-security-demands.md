---
title: 'CA2143: Transparent メソッドはセキュリティ確認要求を使用できません |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: bcfce9a80d02e525212d3f59173df4a7e8fbe968
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662697"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143: 透過的メソッドは、セキュリティ確認要求を使用してはならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 指定された親型またはメソッドは、宣言によって <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> `.Demand` 要求でマークされるか、メソッドが <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName> メソッドを呼び出します。

## <a name="rule-description"></a>規則の説明
 透過的セキュリティ コードでは、操作のセキュリティ検証を行うことができないため、アクセス許可を要求できません。 透過的セキュリティ コードは、フル アクセス要求を使用して、セキュリティ上の決定を行う必要があります。セーフ クリティカルなコードでは、透過的なコードを使用してフル アクセス要求を行うことはできません。 セキュリティチェックを実行するすべてのコード (セキュリティ要求など) は、安全にクリティカルである必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 一般に、この規則違反を修正するには、メソッドを <xref:System.Security.SecuritySafeCriticalAttribute> 属性でマークします。 また、要求を削除することもできます。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 透過的なメソッドが宣言型のセキュリティ要求を行うため、次のコードに規則ファイルがあります。

 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2143.transparentmethodsshouldnotdemand/cs/ca2143 - transparentmethodsshouldnotdemand.cs#1)]

## <a name="see-also"></a>参照
 [CA2142: 透過的コードは、LinkDemand を使用して保護されてはならない](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)

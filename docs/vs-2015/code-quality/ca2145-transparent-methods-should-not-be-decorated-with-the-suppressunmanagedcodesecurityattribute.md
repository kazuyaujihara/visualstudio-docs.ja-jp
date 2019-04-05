---
title: CA2145:透過的なメソッドが、SuppressUnmanagedCodeSecurityAttribute で修飾されていない必要があります |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b6a7c1b5684181098ef0bec1cde430f401ba1136
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "58963713"
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145:透過的メソッドを SuppressUnmanagedCodeSecurityAttribute で修飾してはならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|
|CheckId|CA2145|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 マークされているメソッドでは、透過的なメソッド、<xref:System.Security.SecuritySafeCriticalAttribute>メソッド、またはメソッドが含まれる型が付いて、<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>属性。

## <a name="rule-description"></a>規則の説明
 修飾されたメソッド、<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>属性がメソッド呼び出しに対してされる暗黙的な LinkDemand があります。 この LinkDemand では、呼び出し元のコードがセキュリティ クリティカルなコードである必要があります。 SuppressUnmanagedCodeSecurity を使用するメソッドをマークする、<xref:System.Security.SecurityCriticalAttribute>属性は、メソッドの呼び出し元に対してこの要件をより明確です。

## <a name="how-to-fix-violations"></a>違反の修正方法
 このルールの違反を修正するには、メソッドをマークまたは型を<xref:System.Security.SecurityCriticalAttribute>属性。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

### <a name="code"></a>コード
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2145.transparentmethodsshouldnotusesuppressunmanagedcodesecurity/cs/ca2145.cs#1)]

### <a name="comments"></a>コメント

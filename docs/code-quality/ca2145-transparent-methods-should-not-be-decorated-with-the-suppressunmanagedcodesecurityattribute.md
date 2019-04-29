---
title: CA2145:透過的メソッドを SuppressUnmanagedCodeSecurityAttribute で修飾してはならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a9269a0862dacf928cffb31f722f382271d5f0e7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62542120"
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145:透過的メソッドを SuppressUnmanagedCodeSecurityAttribute で修飾してはならない

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

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。

### <a name="code"></a>コード

[!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute_1.cs)]
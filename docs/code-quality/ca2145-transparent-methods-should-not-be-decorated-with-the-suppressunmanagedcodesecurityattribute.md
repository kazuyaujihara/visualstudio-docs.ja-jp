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
ms.openlocfilehash: 3cca385c346a7daa8aaddb377f999506ffb1abaa
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232049"
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145:透過的メソッドを SuppressUnmanagedCodeSecurityAttribute で修飾してはならない

|||
|-|-|
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|
|CheckId|CA2145|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

透過的メソッド、 <xref:System.Security.SecuritySafeCriticalAttribute>メソッドでマークされたメソッド、またはメソッドを含む型は、 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>属性でマークされます。

## <a name="rule-description"></a>規則の説明

<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>属性で修飾されたメソッドには、それを呼び出すメソッドに配置される暗黙的な LinkDemand があります。 この LinkDemand では、呼び出し元のコードがセキュリティ クリティカルなコードである必要があります。 SuppressUnmanagedCodeSecurity を使用するメソッドに<xref:System.Security.SecurityCriticalAttribute>属性をマークすると、メソッドの呼び出し元に対してこの要件がより明確になります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、メソッドまたは型を<xref:System.Security.SecurityCriticalAttribute>属性でマークします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。

### <a name="code"></a>コード

[!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute_1.cs)]
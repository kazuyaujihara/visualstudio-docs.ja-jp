---
title: CA2138:透過的メソッドは、SuppressUnmanagedCodeSecurity 属性を持つメソッドを呼び出してはならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2138
ms.assetid: a14c4d32-f079-4f3a-956c-a1657cde0f66
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: d88b2f5c15d51ff840cc6ff116396ffd6b5efd60
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232207"
---
# <a name="ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute"></a>CA2138:透過的メソッドは、SuppressUnmanagedCodeSecurity 属性を持つメソッドを呼び出してはならない

|||
|-|-|
|TypeName|TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods|
|CheckId|CA2138|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
透過的セキュリティメソッドは、 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>属性でマークされたメソッドを呼び出します。

## <a name="rule-description"></a>規則の説明
この規則は、たとえば、P/Invoke (プラットフォーム呼び出し) 呼び出しを使用してネイティブコードを直接呼び出す透過的メソッドに対して適用されます。 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>属性でマークされた P/Invoke メソッドと COM 相互運用メソッドは、呼び出し元のメソッドに対して LinkDemand を実行します。 透過的セキュリティコードは Linkdemand を満たすことができないため、コードでは、SuppressUnmanagedCodeSecurity 属性でマークされたメソッド、または SuppressUnmanagedCodeSecurity 属性でマークされたクラスのメソッドを呼び出すことはできません。 メソッドが失敗するか、要求が完全な要求に変換されます。

この規則<xref:System.MethodAccessException>を違反すると、レベル2のセキュリティ透過性モデルのになり、レベル1の<xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A>透過性モデルのに対する完全な要求が発生します。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するに<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> <xref:System.Security.SecurityCriticalAttribute>は、属性を削除し、メソッドを<xref:System.Security.SecuritySafeCriticalAttribute>属性または属性でマークします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
[!code-csharp[FxCop.Security.CA2138.TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods#1](../code-quality/codesnippet/CSharp/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute_1.cs)]
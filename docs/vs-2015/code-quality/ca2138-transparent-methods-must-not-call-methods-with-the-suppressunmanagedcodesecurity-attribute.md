---
title: 'CA2138: Transparent メソッドは、SuppressUnmanagedCodeSecurity attribute | を使用してメソッドを呼び出すことはできません。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2138
ms.assetid: a14c4d32-f079-4f3a-956c-a1657cde0f66
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 65e00d319bff3bbfd3c441c6b60ed8a703e69251
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654815"
---
# <a name="ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute"></a>CA2138: 透過的メソッドは、SuppressUnmanagedCodeSecurity 属性を持つメソッドを呼び出してはならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods|
|CheckId|CA2138|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 透過的セキュリティメソッドは、<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 属性でマークされたメソッドを呼び出します。

## <a name="rule-description"></a>規則の説明
 この規則は、ネイティブコードを直接呼び出す透過的メソッド (たとえば、P/Invoke (プラットフォーム呼び出し) 呼び出しでを使用するなど) で適用されます。 @No__t_0 属性でマークされた P/Invoke メソッドと COM 相互運用メソッドは、呼び出し元のメソッドに対して LinkDemand を実行します。 透過的セキュリティコードは Linkdemand を満たすことができないため、コードでは、SuppressUnmanagedCodeSecurity 属性でマークされたメソッド、または SuppressUnmanagedCodeSecurity 属性でマークされたクラスのメソッドを呼び出すことはできません。 メソッドが失敗するか、要求が完全な要求に変換されます。

 この規則に違反すると、レベル2のセキュリティ透過性モデルの <xref:System.MethodAccessException> と、レベル1の透過性モデルの <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> に対する完全な要求が発生します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 属性を削除し、<xref:System.Security.SecurityCriticalAttribute> または <xref:System.Security.SecuritySafeCriticalAttribute> 属性を使用してメソッドをマークします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 [!code-csharp[FxCop.Security.CA2138.TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2138.transparentmethodsmustnotcallsuppressunmanagedcodesecuritymethods/cs/ca2138.cs#1)]

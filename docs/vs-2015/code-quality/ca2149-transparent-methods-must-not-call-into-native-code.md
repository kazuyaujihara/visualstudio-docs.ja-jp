---
title: CA2149:透過的メソッドはネイティブ コードを呼び出す必要がありますされません |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2149
ms.assetid: 28951bd7-f3db-4871-99aa-bad68d1ead80
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 37d4ee90f5f8732ff4c42b8b086fa56620b97234
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974598"
---
# <a name="ca2149-transparent-methods-must-not-call-into-native-code"></a>CA2149:透過的メソッドは、ネイティブ コード内に呼び出しを行ってはならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsMustNotCallNativeCode|
|CheckId|CA2149|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 メソッドは、P/invoke などのメソッド スタブを使用してネイティブ関数を呼び出します。

## <a name="rule-description"></a>規則の説明
 この規則は、P/Invoke などを使用してネイティブ コードを直接呼び出すすべての透過的メソッドに対して適用されます。 この規則に違反が発生、<xref:System.MethodAccessException>レベル 2 の透過性モデルとの完全な要求で<xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A>レベル 1 の透過性モデルでします。

## <a name="how-to-fix-violations"></a>違反の修正方法
 このルールの違反を修正するには、マークのメソッドを呼び出すネイティブ コードと、<xref:System.Security.SecurityCriticalAttribute>または<xref:System.Security.SecuritySafeCriticalAttribute>属性。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 [!code-csharp[FxCop.Security.CA2149.TransparentMethodsMustNotCallNativeCode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2149.transparentmethodsmustnotcallnativecode/cs/ca2149 - transparentmethodsmustnotcallnativecode.cs#1)]

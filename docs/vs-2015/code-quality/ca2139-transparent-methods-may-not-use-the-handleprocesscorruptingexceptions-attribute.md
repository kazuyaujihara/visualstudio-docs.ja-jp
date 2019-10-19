---
title: 'CA2139: Transparent メソッドは、HandleProcessCorruptingExceptions attribute | を使用することはできません。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2139
ms.assetid: 45a0328a-add7-40f9-8934-dff59beb02b3
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 821598d7708fa8681f1dbc5fee65978d7498dbb5
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72603000"
---
# <a name="ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute"></a>CA2139: 透過的メソッドは、HandleProcessCorruptingExceptions 属性を使用してはならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsMustNotHandleProcessCorruptingExceptions|
|CheckId|CA2139|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 Transparent メソッドは、<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 属性でマークされます。

## <a name="rule-description"></a>規則の説明
 この規則は、透過的なメソッドをすべて実行し、<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 属性を使用して例外の処理を処理しようとします。 プロセスを破損させる例外は、CLR バージョン4.0 の例外 (<xref:System.AccessViolationException> など) の例外の分類です。 HandleProcessCorruptedStateExceptionsAttribute 属性はセキュリティ クリティカルなメソッドでのみ使用できる属性で、透過的メソッドに適用された場合は無視されます。 プロセス破損例外を処理するには、この方法がセキュリティクリティカルまたはセキュリティセーフクリティカルである必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 属性を削除するか、<xref:System.Security.SecurityCriticalAttribute> または <xref:System.Security.SecuritySafeCriticalAttribute> 属性を使用してメソッドをマークします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 この例では、transparent メソッドが <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 属性でマークされているため、ルールは失敗します。 また、メソッドは、<xref:System.Security.SecurityCriticalAttribute> または <xref:System.Security.SecuritySafeCriticalAttribute> 属性でマークする必要があります。

 [!code-csharp[FxCop.Security.CA2139.TransparentMethodsMustNotHandleProcessCorruptingExceptions#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2139.transparentmethodsmustnothandleprocesscorruptingexceptions/cs/ca2139 - transparentmethodsmustnothandleprocesscorruptingexceptions.cs#1)]

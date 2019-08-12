---
title: CA2139:透過的メソッドは、HandleProcessCorruptingExceptions 属性を使用してはならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2139
ms.assetid: 45a0328a-add7-40f9-8934-dff59beb02b3
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f6808c5e9b5d35ab6ec8d4012f08e15cba9a159d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920564"
---
# <a name="ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute"></a>CA2139:透過的メソッドは、HandleProcessCorruptingExceptions 属性を使用してはならない

|||
|-|-|
|TypeName|TransparentMethodsMustNotHandleProcessCorruptingExceptions|
|CheckId|CA2139|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
透過的メソッドは、 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>属性でマークされます。

## <a name="rule-description"></a>規則の説明
この規則は、透過的なメソッドをすべて実行し、 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>属性を使用して例外の処理を処理しようとします。 プロセスを破損させる例外は、CLR バージョン4.0 の例外の<xref:System.AccessViolationException>例外分類です。 HandleProcessCorruptedStateExceptionsAttribute 属性はセキュリティ クリティカルなメソッドでのみ使用できる属性で、透過的メソッドに適用された場合は無視されます。 プロセス破損例外を処理するには、この方法がセキュリティクリティカルまたはセキュリティセーフクリティカルである必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>属性を削除するか、 <xref:System.Security.SecurityCriticalAttribute>または<xref:System.Security.SecuritySafeCriticalAttribute>属性を使用してメソッドをマークします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
この例では、透過的なメソッドは<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>属性でマークされ、ルールは失敗します。 メソッドは、 <xref:System.Security.SecurityCriticalAttribute> <xref:System.Security.SecuritySafeCriticalAttribute>または属性でもマークされている必要があります。

[!code-csharp[FxCop.Security.CA2139.TransparentMethodsMustNotHandleProcessCorruptingExceptions#1](../code-quality/codesnippet/CSharp/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute_1.cs)]
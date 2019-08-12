---
title: CA2142:透過的コードは、LinkDemand を使用して保護されてはならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf5bb8320a8876582cc325ecf973c83593777193
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920494"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142:透過的コードは、LinkDemand を使用して保護されてはならない

|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
透過的な方法で<xref:System.Security.Permissions.SecurityAction>は、または他のセキュリティ要求が必要です。

## <a name="rule-description"></a>規則の説明
この規則は、アクセスするために Linkdemand を必要とする透過的メソッドで発生します。 透過的セキュリティ コードでは、操作のセキュリティ検証を行うことができないため、アクセス許可を要求できません。 透過的な方法はセキュリティに中立的であると想定されているため、セキュリティ上の決定を行うべきではありません。 また、セキュリティ上の決定を行うセーフクリティカルコードは、以前にこのような決定を行った透過的なコードに依存しないようにする必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、透過的なメソッドのリンク確認要求を削除するか<xref:System.Security.SecuritySafeCriticalAttribute> 、セキュリティ要求などのセキュリティチェックを実行している場合は、属性を使用してメソッドをマークします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例では、メソッドに対して規則が適用され<xref:System.Security.PermissionSet> <xref:System.Security.Permissions.SecurityAction>ます。これは、メソッドが透過的であり、を含む LinkDemand でマークされているためです。

[!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]

この規則による警告は抑制しないでください。
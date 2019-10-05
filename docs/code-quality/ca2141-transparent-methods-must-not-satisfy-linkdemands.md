---
title: 'CA2141: 透過的メソッドは、LinkDemand を満たしてはならない'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0365d82917b8cfbaf291d557a6ac2d95c220562a
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232129"
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141: 透過的メソッドは、LinkDemand を満たしてはならない

|||
|-|-|
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
透過的セキュリティメソッドは、 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 属性でマークされていないアセンブリ内のメソッドを呼び出します。または、透過的セキュリティメソッドは、型またはメソッドに対してを<xref:System.Security.Permissions.SecurityAction> `.LinkDemand`満たします。

## <a name="rule-description"></a>規則の説明
LinkDemand を満たすことは、セキュリティ上重要な操作であり、意図しない特権の昇格を引き起こす可能性があります。 透過的セキュリティコードは、セキュリティクリティカルなコードと同じセキュリティ監査要件の対象にならないため、Linkdemand を満たしてはなりません。 セキュリティ規則セットレベル1のアセンブリの透過的メソッドによって、対応するすべての Linkdemand が実行時に完全な要求に変換され、パフォーマンスの問題が発生する可能性があります。 セキュリティ規則セットレベル2のアセンブリでは、LinkDemand を満たす場合、transparent メソッドはジャストインタイム (JIT) コンパイラでのコンパイルに失敗します。

レベル2のセキュリティを使用するアセンブリでは、セキュリティ transparent メソッドによって linkdemand を満たすか、非 APTCA アセンブリのメソッドを呼び出す<xref:System.MethodAccessException>と、が発生します。レベル1のアセンブリでは、LinkDemand は完全な要求になります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するに<xref:System.Security.SecurityCriticalAttribute>は、アクセスメソッドを属性または<xref:System.Security.SecuritySafeCriticalAttribute>属性でマークするか、アクセスされたメソッドから LinkDemand を削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
この例では、transparent メソッドは LinkDemand を持つメソッドを呼び出そうとします。 このルールは、このコードで発生します。

[!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../code-quality/codesnippet/CSharp/ca2141-transparent-methods-must-not-satisfy-linkdemands_1.cs)]
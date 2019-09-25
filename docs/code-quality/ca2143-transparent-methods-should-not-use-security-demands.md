---
title: CA2143:透過的メソッドは、セキュリティ確認要求を使用してはならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a182beba738e583fad83c3f51d7efa312761906d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231980"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143:透過的メソッドは、セキュリティ確認要求を使用してはならない

|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
指定された親型またはメソッドは、 <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>宣言によって`.Demand`要求に<xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName>よってマークされるか、メソッドがメソッドを呼び出します。

## <a name="rule-description"></a>規則の説明
透過的セキュリティ コードでは、操作のセキュリティ検証を行うことができないため、アクセス許可を要求できません。 透過的セキュリティ コードは、フル アクセス要求を使用して、セキュリティ上の決定を行う必要があります。セーフ クリティカルなコードでは、透過的なコードを使用してフル アクセス要求を行うことはできません。 セキュリティチェックを実行するすべてのコード (セキュリティ要求など) は、安全にクリティカルである必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
一般に、この規則違反を修正するには、メソッドを<xref:System.Security.SecuritySafeCriticalAttribute>属性でマークします。 また、要求を削除することもできます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
透過的なメソッドが宣言型のセキュリティ要求を行うため、次のコードに規則ファイルがあります。

[!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../code-quality/codesnippet/CSharp/ca2143-transparent-methods-should-not-use-security-demands_1.cs)]

## <a name="see-also"></a>関連項目
[CA2142透過的なコードを Linkdemand で保護することはできません](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)
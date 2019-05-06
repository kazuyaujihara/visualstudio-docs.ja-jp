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
ms.openlocfilehash: 17160e5fd47491dddb22a28d4b3f7464ad3efb78
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806790"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143:透過的メソッドは、セキュリティ確認要求を使用してはならない

|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 透明の型またはメソッドでマークされた宣言によって、 <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> `.Demand`オンデマンドまたはメソッドの呼び出し、<xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName>メソッド。

## <a name="rule-description"></a>規則の説明
 透過的セキュリティ コードでは、操作のセキュリティ検証を行うことができないため、アクセス許可を要求できません。 透過的セキュリティ コードは、フル アクセス要求を使用して、セキュリティ上の決定を行う必要があります。セーフ クリティカルなコードでは、透過的なコードを使用してフル アクセス要求を行うことはできません。 セキュリティ確認要求などのセキュリティ チェックを実行するコードは、代わりにセーフ クリティカルにする必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 一般に、この規則の違反を修正するを持つメソッドをマーク、<xref:System.Security.SecuritySafeCriticalAttribute>属性。 要求を削除することもできます。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 ルールは、透過的メソッドは、宣言型のセキュリティ確認要求するため、次のコードをファイルします。

 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../code-quality/codesnippet/CSharp/ca2143-transparent-methods-should-not-use-security-demands_1.cs)]

## <a name="see-also"></a>関連項目
 [CA2142:LinkDemands を透過的なコードを保護する必要がありません。](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)
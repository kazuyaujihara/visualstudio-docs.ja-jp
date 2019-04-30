---
title: CA2126:型のリンク要求には継承要求が必要です
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2fdf92eae202f1ebb80b88e28307e7dacfbc0a39
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62542391"
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126:型のリンク要求には継承要求が必要です

|||
|-|-|
|TypeName|TypeLinkDemandsRequireInheritanceDemands|
|CheckId|CA2126|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリックの封印されていない型が保護されているリンク確認要求、オーバーライド可能なメソッドを持つし、型でも、メソッドが継承確認要求で保護されています。

## <a name="rule-description"></a>規則の説明
 メソッドまたはその宣言型のリンク確認要求では、指定したアクセス許可が、メソッドの直接の呼び出し元が必要です。 メソッドの継承確認要求では、指定したアクセス許可がオーバーライドするメソッドが必要です。 型の継承確認要求では、指定した権限を持っているために派生クラスが必要です。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するのには、型またはリンク確認要求と同じアクセス許可の継承確認要求でメソッドをセキュリティで保護します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、規則に違反する型を示します。

 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]

## <a name="related-rules"></a>関連するルール
 [CA 2108:値型で宣言型セキュリティを確認してください。](../code-quality/ca2108-review-declarative-security-on-value-types.md)

 [CA 2112:セキュリティで保護された型はフィールドを公開する必要があります。](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA 2122:リンク確認要求でメソッドを間接的に公開できません。](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

 [CA2123:オーバーライドのリンク確認要求は基本同一である必要があります。](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>関連項目

- [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)
- [リンク確認要求](/dotnet/framework/misc/link-demands)
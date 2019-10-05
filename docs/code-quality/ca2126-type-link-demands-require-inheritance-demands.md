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
ms.openlocfilehash: 4f01ba5af7640521333093e4bba1f36a95363b60
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232461"
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126:型のリンク要求には継承要求が必要です

|||
|-|-|
|TypeName|TypeLinkDemandsRequireInheritanceDemands|
|CheckId|CA2126|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリックに封印されていない型はリンク確認要求で保護され、オーバーライド可能なメソッドを持っています。また、型もメソッドも継承要求で保護されていません。

## <a name="rule-description"></a>規則の説明
メソッドまたはその宣言する型に対するリンク確認要求を行うには、メソッドの直前の呼び出し元に、指定されたアクセス許可が必要です。 メソッドに対する継承要求では、指定されたアクセス許可を持つオーバーライドメソッドが必要です。 型に対する継承要求では、指定されたアクセス許可を持つ派生クラスが必要です。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、リンク確認要求と同じアクセス許可の継承要求で、型またはメソッドをセキュリティで保護します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、規則に違反する型を示しています。

[!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
[!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
[!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA2108値型の宣言セキュリティを確認する](../code-quality/ca2108-review-declarative-security-on-value-types.md)

[CA2112セキュリティで保護された型はフィールドを公開しません](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

[CA2122リンク確認要求で間接的にメソッドを公開しない](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

[CA2123オーバーライドリンク確認要求は基本と同じである必要があります](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>関連項目

- [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)
- [リンク確認要求](/dotnet/framework/misc/link-demands)
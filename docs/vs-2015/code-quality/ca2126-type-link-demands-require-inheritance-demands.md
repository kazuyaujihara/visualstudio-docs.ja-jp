---
title: CA2126:種類のリンク要求継承要求が必要です |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8aee10059e9c50e7f572c6fb784da7b97f323905
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65687236"
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126:型のリンク要求には継承要求が必要です
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、規則に違反する型を示します。

 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesWithLinkDemands/cpp/FxCop.Security.TypesWithLinkDemands.cpp#1)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesWithLinkDemands/cs/FxCop.Security.TypesWithLinkDemands.cs#1)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Security.TypesWithLinkDemands/vb/FxCop.Security.TypesWithLinkDemands.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA 2108:値型で宣言型セキュリティを確認してください。](../code-quality/ca2108-review-declarative-security-on-value-types.md)

 [CA 2112:セキュリティで保護された型はフィールドを公開する必要があります。](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA 2122:リンク確認要求でメソッドを間接的に公開できません。](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

 [CA2123:オーバーライドのリンク確認要求は基本同一である必要があります。](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>関連項目
 [安全なコーディングのガイドライン](https://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)[継承確認要求](https://msdn.microsoft.com/28b9adbb-8f08-4f10-b856-dbf59eb932d9)[リンク確認要求](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)[要求](https://msdn.microsoft.com/e5283e28-2366-4519-b27d-ef5c1ddc1f48)

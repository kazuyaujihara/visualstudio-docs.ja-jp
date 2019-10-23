---
title: 'CA1055: URI 戻り値を文字列にすることはできません |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1055
- UriReturnValuesShouldNotBeStrings
helpviewer_keywords:
- UriReturnValuesShouldNotBeStrings
- CA1055
ms.assetid: 40e39873-7872-4988-8195-9eb0ade9ece0
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 1817d8aa51f1e47e23a7b5ee79580c44f3fe521f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72603237"
---
# <a name="ca1055-uri-return-values-should-not-be-strings"></a>CA1055: URI 戻り値を文字列にすることはできません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UriReturnValuesShouldNotBeStrings|
|CheckId|CA1055|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 メソッドの名前には、"uri"、"Uri"、"urn"、"Urn"、"url"、または "Url" が含まれ、メソッドは文字列を返します。

## <a name="rule-description"></a>規則の説明
 このルールは、Pascal 形式の表記規則に基づいてメソッド名をトークンに分割し、各トークンが "uri"、"Uri"、"urn"、"Urn"、"url"、または "Url" に等しいかどうかを確認します。 一致するものがある場合、この規則は、メソッドが URI (uniform resource identifier) を返すことを前提としています。 URI の文字列表現は解析エラーやエンコーディング エラーが発生しやすく、セキュリティ上の脆弱性の原因となる場合があります。 @No__t_0 クラスは、これらのサービスを安全かつ安全な方法で提供します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、戻り値の型を <xref:System.Uri> に変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 戻り値が URI を表していない場合は、この規則からの警告を抑制することが安全です。

## <a name="example"></a>例
 次の例では、この規則に違反する型を `ErrorProne`、規則を満たす型 `SaferWay` を示しています。

 [!code-cpp[FxCop.Design.UriNotString#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/cpp/FxCop.Design.UriNotString.cpp#1)]
 [!code-csharp[FxCop.Design.UriNotString#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/cs/FxCop.Design.UriNotString.cs#1)]
 [!code-vb[FxCop.Design.UriNotString#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/vb/FxCop.Design.UriNotString.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1056: URI プロパティを文字列にすることはできません](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: URI パラメーターを文字列にすることはできません](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA2234: 文字列の代わりに System.Uri オブジェクトを渡します](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1057: 文字列 URI オーバーロードが、System.Uri オーバーロードを呼び出します](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)

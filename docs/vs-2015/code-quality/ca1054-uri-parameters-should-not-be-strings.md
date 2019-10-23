---
title: 'CA1054: URI パラメーターを文字列にすることはできません |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1054
- UriParametersShouldNotBeStrings
helpviewer_keywords:
- CA1054
- UriParametersShouldNotBeStrings
ms.assetid: 8e99d72b-a658-47a7-8dd5-9784ce2c30b8
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 2062c7518545300074a0377b7a9cca7ddf1a8aa5
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72603377"
---
# <a name="ca1054-uri-parameters-should-not-be-strings"></a>CA1054: URI パラメーターを文字列にすることはできません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UriParametersShouldNotBeStrings|
|CheckId|CA1054|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 型は、名前に "uri"、"Uri"、"urn"、"Urn"、"url"、または "Url" を含む文字列パラメーターを持つメソッドを宣言します。型は、<xref:System.Uri?displayProperty=fullName> パラメーターを受け取る対応するオーバーロードを宣言しません。

## <a name="rule-description"></a>規則の説明
 このルールでは、camel 形式の表記規則に基づいてパラメーター名をトークンに分割し、各トークンが "uri"、"Uri"、"urn"、"Urn"、"url"、または "Url" に等しいかどうかを確認します。 一致するものがある場合、このルールは、パラメーターが URI (uniform resource identifier) を表すことを前提としています。 URI の文字列表現は解析エラーやエンコーディング エラーが発生しやすく、セキュリティ上の脆弱性の原因となる場合があります。 メソッドが URI の文字列表現を受け取る場合は、対応するオーバーロードを指定して <xref:System.Uri> クラスのインスタンスを取得する必要があります。これにより、これらのサービスが安全かつ安全な方法で提供されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、パラメーターを <xref:System.Uri> 型に変更します。これは、互換性に影響する変更点です。 または、<xref:System.Uri> パラメーターを受け取るメソッドのオーバーロードを指定します。これは、互換性のない変更です。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 パラメーターが URI を表していない場合は、この規則からの警告を抑制することが安全です。

## <a name="example"></a>例
 次の例では、この規則に違反する型を `ErrorProne`、規則を満たす型 `SaferWay` を示しています。

 [!code-cpp[FxCop.Design.UriNotString#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/cpp/FxCop.Design.UriNotString.cpp#1)]
 [!code-csharp[FxCop.Design.UriNotString#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/cs/FxCop.Design.UriNotString.cs#1)]
 [!code-vb[FxCop.Design.UriNotString#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/vb/FxCop.Design.UriNotString.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1056: URI プロパティを文字列にすることはできません](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1055: URI 戻り値を文字列にすることはできません](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)

 [CA2234: 文字列の代わりに System.Uri オブジェクトを渡します](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1057: 文字列 URI オーバーロードが、System.Uri オーバーロードを呼び出します](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)

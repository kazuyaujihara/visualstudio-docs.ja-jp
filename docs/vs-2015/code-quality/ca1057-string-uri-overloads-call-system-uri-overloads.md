---
title: 'CA1057: 文字列 URI のオーバーロードは、System. Uri overloads | を呼び出します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1057
- StringUriOverloadsCallSystemUriOverloads
helpviewer_keywords:
- StringUriOverloadsCallSystemUriOverloads
- CA1057
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: ba7e7de4f3ef6336ed3d82dc1e1da03ec0bf2575
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72603079"
---
# <a name="ca1057-string-uri-overloads-call-systemuri-overloads"></a>CA1057: 文字列 URI オーバーロードが、System.Uri オーバーロードを呼び出します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|StringUriOverloadsCallSystemUriOverloads|
|CheckId|CA1057|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 型は、文字列パラメーターの置換によってのみ異なるメソッドオーバーロードを <xref:System.Uri?displayProperty=fullName> パラメーターに宣言します。文字列パラメーターを受け取るオーバーロードは、<xref:System.Uri> パラメーターを受け取るオーバーロードを呼び出しません。

## <a name="rule-description"></a>規則の説明
 オーバーロードは string/<xref:System.Uri> パラメーターによってのみ異なるため、文字列は URI (uniform resource identifier) を表すと見なされます。 URI の文字列表現は解析エラーやエンコーディング エラーが発生しやすく、セキュリティ上の脆弱性の原因となる場合があります。 @No__t_0 クラスは、これらのサービスを安全かつ安全な方法で提供します。 @No__t_0 クラスの利点を得るために、文字列のオーバーロードでは、文字列引数を使用して <xref:System.Uri> オーバーロードを呼び出す必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 URI の文字列表現を使用するメソッドを再実装します。これにより、文字列引数を使用して <xref:System.Uri> クラスのインスタンスが作成され、<xref:System.Uri> オブジェクトが <xref:System.Uri> パラメーターを持つオーバーロードに渡されます。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 文字列パラメーターが URI を表していない場合は、この規則からの警告を抑制することが安全です。

## <a name="example"></a>例
 次の例は、正しく実装された文字列オーバーロードを示しています。

 [!code-cpp[FxCop.Design.CallUriOverload#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload/cpp/FxCop.Design.CallUriOverload.cpp#1)]
 [!code-csharp[FxCop.Design.CallUriOverload#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload/cs/FxCop.Design.CallUriOverload.cs#1)]
 [!code-vb[FxCop.Design.CallUriOverload#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload/vb/FxCop.Design.CallUriOverload.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA2234: 文字列の代わりに System.Uri オブジェクトを渡します](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1056: URI プロパティを文字列にすることはできません](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: URI パラメーターを文字列にすることはできません](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055: URI 戻り値を文字列にすることはできません](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)

---
title: 'CA1057: 文字列 URI オーバーロードが、System.Uri オーバーロードを呼び出します'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1057
- StringUriOverloadsCallSystemUriOverloads
helpviewer_keywords:
- StringUriOverloadsCallSystemUriOverloads
- CA1057
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: dd79751c67ca5540cb22eb692b2d11c0941005a6
ms.sourcegitcommit: 1507baf3a336bbb6511d4c3ce73653674831501b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72349044"
---
# <a name="ca1057-string-uri-overloads-call-systemuri-overloads"></a>CA1057: 文字列 URI オーバーロードが、System.Uri オーバーロードを呼び出します

|||
|-|-|
|TypeName|StringUriOverloadsCallSystemUriOverloads|
|CheckId|CA1057|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

型は、文字列パラメーターの置換によってのみ異なるメソッドオーバーロードを <xref:System.Uri?displayProperty=fullName> パラメーターに宣言します。文字列パラメーターを受け取るオーバーロードは、<xref:System.Uri> パラメーターを受け取るオーバーロードを呼び出しません。

## <a name="rule-description"></a>規則の説明
オーバーロードは文字列または <xref:System.Uri> パラメーターのみが異なるため、文字列は URI (uniform resource identifier) を表すと見なされます。 URI の文字列表現は解析エラーやエンコーディング エラーが発生しやすく、セキュリティ上の脆弱性の原因となる場合があります。 @No__t-0 クラスは、これらのサービスを安全かつ安全な方法で提供します。 @No__t 0 クラスの利点を得るために、文字列のオーバーロードでは、文字列引数を使用して <xref:System.Uri> オーバーロードを呼び出す必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
URI の文字列形式を使用するメソッドを再実装して、文字列引数を使用して <xref:System.Uri> クラスのインスタンスを作成し、<xref:System.Uri> オブジェクトを <xref:System.Uri> パラメーターを持つオーバーロードに渡します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
文字列パラメーターが URI を表していない場合は、この規則からの警告を抑制することが安全です。

## <a name="example"></a>例
次の例は、正しく実装された文字列オーバーロードを示しています。

[!code-csharp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CSharp/ca1057-string-uri-overloads-call-system-uri-overloads_1.cs)]
[!code-cpp[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/CPP/ca1057-string-uri-overloads-call-system-uri-overloads_1.cpp)]
[!code-vb[FxCop.Design.CallUriOverload#1](../code-quality/codesnippet/VisualBasic/ca1057-string-uri-overloads-call-system-uri-overloads_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA2234: 文字列の代わりに System.Uri オブジェクトを渡します](../code-quality/ca2234.md)

[CA1056: URI プロパティを文字列にすることはできません](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

[CA1054: URI パラメーターを文字列にすることはできません](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

[CA1055: URI 戻り値を文字列にすることはできません](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)
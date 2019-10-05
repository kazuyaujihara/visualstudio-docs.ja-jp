---
title: CA1054:URI パラメーターを文字列にすることはできません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1054
- UriParametersShouldNotBeStrings
helpviewer_keywords:
- CA1054
- UriParametersShouldNotBeStrings
ms.assetid: 8e99d72b-a658-47a7-8dd5-9784ce2c30b8
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 49788b900eb8aed9fac6e4da4844377bae67efbf
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235556"
---
# <a name="ca1054-uri-parameters-should-not-be-strings"></a>CA1054:URI パラメーターを文字列にすることはできません

|||
|-|-|
|TypeName|UriParametersShouldNotBeStrings|
|CheckId|CA1054|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型は、名前に "uri"、"uri"、"urn"、"urn"、"url"、または "url" を含む文字列パラメーターを持つメソッドを宣言します。型は、パラメーターを<xref:System.Uri?displayProperty=fullName>受け取る対応するオーバーロードを宣言しません。

既定では、この規則は外部から参照できる型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

このルールでは、camel 形式の表記規則に基づいてパラメーター名をトークンに分割し、各トークンが "uri"、"Uri"、"urn"、"Urn"、"url"、または "Url" に等しいかどうかを確認します。 一致するものがある場合、このルールは、パラメーターが URI (uniform resource identifier) を表すことを前提としています。 URI の文字列表現は解析エラーやエンコーディング エラーが発生しやすく、セキュリティ上の脆弱性の原因となる場合があります。 メソッドが URI の文字列表現を受け取る場合は、対応するオーバーロードを指定して、 <xref:System.Uri>クラスのインスタンスを取得する必要があります。これにより、これらのサービスが安全かつ安全な方法で提供されます。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、パラメーターを<xref:System.Uri>型に変更します。これは互換性に影響する変更です。 または、パラメーターを<xref:System.Uri>受け取るメソッドのオーバーロードを指定します。これは、非互換性に影響する変更です。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

パラメーターが URI を表さない場合、この規則からの警告を抑制するのは安全です。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1054.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example"></a>例

次の例は、この規則`ErrorProne`に違反する型と、規則を満たす`SaferWay`型を示しています。

[!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1054-uri-parameters-should-not-be-strings_1.cs)]
[!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1054-uri-parameters-should-not-be-strings_1.vb)]
[!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1054-uri-parameters-should-not-be-strings_1.cpp)]

## <a name="related-rules"></a>関連するルール

- [CA1056URI プロパティを文字列にすることはできません](../code-quality/ca1056-uri-properties-should-not-be-strings.md)
- [CA1055URI 戻り値を文字列にすることはできません](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)
- [CA2234文字列ではなく、システムの Uri オブジェクトを渡す](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)
- [CA1057文字列 URI のオーバーロードは、システムの Uri のオーバーロードを呼び出します](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)
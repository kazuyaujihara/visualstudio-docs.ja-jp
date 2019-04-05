---
title: CA2234:文字列の代わりに System.Uri オブジェクトを渡す |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ce0ed8a2600d52d3a8f6649a528b6c809895f3fe
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58964050"
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234:文字列の代わりに System.Uri オブジェクトを渡します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|PassSystemUriObjectsInsteadOfStrings|
|CheckId|CA2234|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 名前持つにはには、"uri"、"Uri"、"urn"、"Urn"、"url"または"Url"; が含まれています。 文字列パラメーターを持つメソッドの呼び出しメソッドの宣言する型には持つ対応するメソッド オーバー ロードが含まれています、<xref:System.Uri?displayProperty=fullName>パラメーター。

## <a name="rule-description"></a>規則の説明
 パラメーター名は camel 規約に基づくトークンに分割し、各トークンが"uri"、"Uri"、"urn"、"Urn"、"url"または"Url"と等しいかどうかを確認するチェックします。 一致がある場合は、uniform resource identifier (URI) を表すパラメーターが使用されます。 URI の文字列表現は解析エラーやエンコーディング エラーが発生しやすく、セキュリティ上の脆弱性の原因となる場合があります。 <xref:System.Uri>クラスは、安全かつセキュリティで保護された方法でこれらのサービスを提供します。 URI の形式に関するのみが異なる 2 つのオーバー ロードの間で、選択した場合は、ユーザーを受け取るオーバー ロードを選択する必要があります、<xref:System.Uri>引数。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則の違反を修正するには、使用するオーバー ロードを呼び出す、<xref:System.Uri>引数。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 文字列パラメーターが URI を表していない場合、この規則による警告を抑制するのには安全です。

## <a name="example"></a>例
 次の例では、メソッド、 `ErrorProne`、ルールと、メソッドに違反して`SaferWay`を正しく呼び出し、<xref:System.Uri>オーバー ロードします。

 [!code-cpp[FxCop.Usage.PassUri#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.PassUri/cpp/FxCop.Usage.PassUri.cpp#1)]
 [!code-csharp[FxCop.Usage.PassUri#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.PassUri/cs/FxCop.Usage.PassUri.cs#1)]
 [!code-vb[FxCop.Usage.PassUri#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.PassUri/vb/FxCop.Usage.PassUri.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA 1057:文字列 URI オーバー ロードは、System.Uri オーバー ロードを呼び出す](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)

 [CA 1056:URI のプロパティには、文字列がすることはできません。](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA 1054:URI パラメーターは文字列をすることはできません。](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA 1055:URI 戻り値は文字列をすることはできません。](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)

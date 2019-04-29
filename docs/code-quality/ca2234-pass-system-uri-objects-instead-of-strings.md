---
title: CA2234:文字列の代わりに System.Uri オブジェクトを渡します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 97b73793d0c473727960dbde8fe32fc584ff6dd5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541697"
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234:文字列の代わりに System.Uri オブジェクトを渡します

|||
|-|-|
|TypeName|PassSystemUriObjectsInsteadOfStrings|
|CheckId|CA2234|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

名前持つにはには、"uri"、"Uri"、"urn"、"Urn"、"url"または"Url"が含まれています。 文字列パラメーターを持つメソッドの呼び出しとメソッドの宣言する型を持つ対応するメソッド オーバー ロードが含まれています、<xref:System.Uri?displayProperty=fullName>パラメーター。

既定では、このルールだけが検索で外部から参照できるメソッドと型が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

パラメーター名は camel 規約に基づくトークンに分割し、各トークンが"uri"、"Uri"、"urn"、"Urn"、"url"または"Url"と等しいかどうかを確認するチェックします。 一致がある場合は、uniform resource identifier (URI) を表すパラメーターが使用されます。 URI の文字列表現は解析エラーやエンコーディング エラーが発生しやすく、セキュリティ上の脆弱性の原因となる場合があります。 <xref:System.Uri>クラスは、安全かつセキュリティで保護された方法でこれらのサービスを提供します。 URI の形式に関するのみが異なる 2 つのオーバー ロードの間で、選択した場合は、ユーザーを受け取るオーバー ロードを選択する必要があります、<xref:System.Uri>引数。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則の違反を修正するには、使用するオーバー ロードを呼び出す、<xref:System.Uri>引数。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

文字列パラメーターが URI を表していない場合、この規則による警告を抑制するのには安全です。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca2234.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (使用) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example"></a>例

次の例では、メソッド、 `ErrorProne`、ルールと、メソッドに違反する`SaferWay`を正しく呼び出す、<xref:System.Uri>オーバー ロードします。

[!code-vb[FxCop.Usage.PassUri#1](../code-quality/codesnippet/VisualBasic/ca2234-pass-system-uri-objects-instead-of-strings_1.vb)]
[!code-cpp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CPP/ca2234-pass-system-uri-objects-instead-of-strings_1.cpp)]
[!code-csharp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CSharp/ca2234-pass-system-uri-objects-instead-of-strings_1.cs)]

## <a name="related-rules"></a>関連するルール

- [CA 1057:文字列 URI オーバー ロードは、System.Uri オーバー ロードを呼び出す](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)
- [CA 1056:URI のプロパティには、文字列がすることはできません。](../code-quality/ca1056-uri-properties-should-not-be-strings.md)
- [CA 1054:URI パラメーターは文字列をすることはできません。](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)
- [CA 1055:URI 戻り値は文字列をすることはできません。](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)
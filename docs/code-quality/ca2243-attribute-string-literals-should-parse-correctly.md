---
title: CA2243:属性文字列リテラルは、正しく解析する必要があります
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2243
- AttributeStringLiteralsShouldParseCorrectly
helpviewer_keywords:
- AttributeStringLiteralsShouldParseCorrectly
- CA2243
ms.assetid: bfadb366-379d-4ee4-b17b-c4a09bf1106b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f9c0f078c21de023b1f5cfacde0cf122c179adb2
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919898"
---
# <a name="ca2243-attribute-string-literals-should-parse-correctly"></a>CA2243:属性文字列リテラルは、正しく解析する必要があります

|||
|-|-|
|TypeName|AttributeStringLiteralsShouldParseCorrectly|
|CheckId|CA2243|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
属性の文字列リテラルパラメーターは、URL、GUID、またはバージョンに対して正しく解析されません。

## <a name="rule-description"></a>規則の説明
属性はから<xref:System.Attribute?displayProperty=fullName>派生しており、属性はコンパイル時に使用されるため、定数値のみをコンストラクターに渡すことができます。 Url、guid、およびバージョンを表す必要がある属性パラメーターを、 <xref:System.Uri?displayProperty=fullName> <xref:System.Guid?displayProperty=fullName>、および<xref:System.Version?displayProperty=fullName>として型指定することはできません。これらの型は定数として表すことができないためです。 代わりに、文字列で表現する必要があります。

パラメーターは文字列として型指定されるため、コンパイル時に正しく書式設定されていないパラメーターが渡される可能性があります。

このルールでは、名前付けヒューリスティックを使用して、uniform resource identifier (URI)、グローバル一意識別子 (GUID)、またはバージョンを表すパラメーターを検索し、渡された値が正しいことを確認します。

## <a name="how-to-fix-violations"></a>違反の修正方法
パラメーター文字列を正しい形式の URL、GUID、またはバージョンに変更してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
パラメーターが URL、GUID、またはバージョンを表していない場合は、この規則による警告を抑制しても安全です。

## <a name="example"></a>例
次の例は、この規則に違反する AssemblyFileVersionAttribute のコードを示しています。

[!code-csharp[FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly#1](../code-quality/codesnippet/CSharp/ca2243-attribute-string-literals-should-parse-correctly_1.cs)]

このルールは、次のパラメーターによってトリガーされます。

- ' Version ' を含むパラメーターは、system.string に解析できません。

- ' Guid ' を含むパラメーターは、System.guid に解析できません。

- ' Uri '、' urn '、または ' url ' を含むパラメーターは、system.string に解析できません。

## <a name="see-also"></a>関連項目

- [CA1054URI パラメーターを文字列にすることはできません](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)
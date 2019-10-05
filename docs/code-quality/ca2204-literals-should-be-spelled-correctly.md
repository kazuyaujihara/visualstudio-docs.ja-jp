---
title: CA2204:リテラルに正しいスペルを要求
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6763fd9f8999bd590511026f6571db6a747c43bc
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231854"
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204:リテラルに正しいスペルを要求

|||
|-|-|
|TypeName|LiteralsShouldBeSpelledCorrectly|
|CheckId|CA2204|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

リテラル文字列は、ローカライズ可能なパラメーターの引数として、またはローカライズ可能なプロパティに渡されます。文字列には、Microsoft スペルチェックライブラリで認識されない1つ以上の単語が含まれています。

## <a name="rule-description"></a>規則の説明

このルールでは、次のケースの1つ以上が当てはまる場合に、パラメーターまたはプロパティに値として渡されるリテラル文字列をチェックします。

- パラメーター <xref:System.ComponentModel.LocalizableAttribute>またはプロパティの属性が true に設定されています。

- パラメーターまたはプロパティ名には、"Text"、"Message"、または "Caption" が含まれています。

- <xref:System.Console.Write%2A>または<xref:System.Console.WriteLine>メソッドに渡される文字列変数の名前は、"value" または "format" のいずれかになります。

このルールは、リテラル文字列を単語に解析し、複合語をトークン化して、各単語またはトークンのスペルをチェックします。 解析アルゴリズムの詳細については[、CA1704 を参照してください。識別子は正しく](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)入力されている必要があります。

## <a name="language"></a>言語

スペルチェックでは、現在、英語ベースのカルチャディクショナリのみがチェックされます。 プロジェクトファイル内のプロジェクトのカルチャを変更するには、 **CodeAnalysisCulture**要素を追加します。

次に例を示します。

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> カルチャを英語ベースのカルチャ以外に設定した場合、このコード分析規則は警告なしで無効になります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、単語のスペルを修正するか、またはカスタム辞書に単語を追加します。 カスタム辞書の使用方法の詳細について[は、「」を参照してください。コード分析辞書](../code-quality/how-to-customize-the-code-analysis-dictionary.md)をカスタマイズします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。 正しい綴りの単語を使用すると、新しいソフトウェアライブラリに必要な学習曲線を減らすことができます。

## <a name="related-rules"></a>関連するルール

- [CA1704識別子は正しく入力されなければなりません](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA1703リソース文字列は正しく入力されなければなりません](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
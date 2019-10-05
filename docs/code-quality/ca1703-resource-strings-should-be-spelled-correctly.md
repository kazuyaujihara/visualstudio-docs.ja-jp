---
title: CA1703:リソース文字列は正しく入力されなければなりません
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: edd3945953a07b10aee5c2690a25aafe446e2c10
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234322"
---
# <a name="ca1703-resource-strings-should-be-spelled-correctly"></a>CA1703:リソース文字列は正しく入力されなければなりません

|||
|-|-|
|TypeName|ResourceStringsShouldBeSpelledCorrectly|
|CheckId|CA1703|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

リソース文字列に Microsoft スペル チェック ライブラリで認識されない語が 1 つ以上含まれています。

## <a name="rule-description"></a>規則の説明

この規則では、リソース文字列を単語 (トークン化複合単語) に解析し、各単語/トークンのスペルをチェックします。 解析アルゴリズムの詳細については[、CA1704 を参照してください。識別子は正しく](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)入力されている必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、正しくスペルが正しい単語を入力するか、カスタム辞書に単語を追加します。 カスタム辞書の使用方法の詳細について[は、「CA1704:識別子は正しく](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)入力されている必要があります。

## <a name="change-the-dictionary-language"></a>辞書の言語を変更する

既定では、スペルチェックの英語 (en) バージョンが使用されます。 スペルチェックの言語を変更するには、 *AssemblyInfo.cs*ファイルまたは*AssemblyInfo*ファイルに次の属性のいずれかを追加します。

- リソース<xref:System.Reflection.AssemblyCultureAttribute>がサテライトアセンブリにある場合は、を使用してカルチャを指定します。
- リソース<xref:System.Resources.NeutralResourcesLanguageAttribute>がコードと同じアセンブリ内にある場合は、を使用して、アセンブリの*ニュートラルカルチャ*を指定します。

> [!IMPORTANT]
> カルチャを英語ベースのカルチャ以外に設定した場合、このコード分析規則は警告なしで無効になります。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。 正しい綴りの単語を指定すると、新しいソフトウェアライブラリの学習に必要な時間が短縮されます。

## <a name="related-rules"></a>関連するルール

- [CA1701リソース文字列の複合語は、大文字と小文字が正しく区別されます。](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1704識別子は正しく入力されなければなりません](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA2204リテラルは正しく入力されなければなりません](../code-quality/ca2204-literals-should-be-spelled-correctly.md)
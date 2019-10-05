---
title: CA1701:リソース文字列の複合語は、大文字と小文字を正しく区別しなければなりません
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- ResourceStringCompoundWordsShouldBeCasedCorrectly
- CA1701
helpviewer_keywords:
- CA1701
- ResourceStringCompoundWordsShouldBeCasedCorrectly
ms.assetid: 4ddbe09f-24b8-4c47-9373-a06f4487ca0d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ed5ae8c0845755fe626e7e801f500389f9263cf5
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234361"
---
# <a name="ca1701-resource-string-compound-words-should-be-cased-correctly"></a>CA1701:リソース文字列の複合語は、大文字と小文字を正しく区別しなければなりません

|||
|-|-|
|TypeName|ResourceStringCompoundWordsShouldBeCasedCorrectly|
|CheckId|CA1701|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

リソース文字列に、大文字小文字が正しく表示されない複合語が含まれています。

## <a name="rule-description"></a>規則の説明

リソース文字列内の各単語は、大文字小文字に基づくトークンに分割されます。 Microsoft スペル チェック ライブラリは、隣接する 2 つのトークンの組み合わせを個別にチェックします。 それらが認識されると、その語はこの規則への違反となります。 違反の原因となる複合語の例としては、"CheckSum" と "マルチパート" があります。これは、それぞれ "Checksum" と "マルチパート" として使用する必要があります。 以前の一般的な使用により、いくつかの例外がルールに組み込まれています。また、"Toolbar" や "Filename" などの複数の単語にフラグが設定されている場合は、2つの異なる単語として大文字にする必要があります。 この例では、"ToolBar" と "FileName" にフラグが設定されています。

名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェア ライブラリを習得するまでの時間を短縮でき、マネージド コード開発の専門家によってライブラリが開発されたという信頼を顧客に与えることができます。

## <a name="how-to-fix-violations"></a>違反の修正方法

大文字と小文字が正しくなるように単語を変更します。

## <a name="change-the-dictionary-language"></a>辞書の言語を変更する

既定では、スペルチェックの英語 (en) バージョンが使用されます。 スペルチェックの言語を変更するには、 *AssemblyInfo.cs*ファイルまたは*AssemblyInfo*ファイルに次の属性のいずれかを追加します。

- リソース<xref:System.Reflection.AssemblyCultureAttribute>がサテライトアセンブリにある場合は、を使用してカルチャを指定します。
- リソース<xref:System.Resources.NeutralResourcesLanguageAttribute>がコードと同じアセンブリ内にある場合は、を使用して、アセンブリの*ニュートラルカルチャ*を指定します。

> [!IMPORTANT]
> カルチャを英語ベースのカルチャ以外に設定した場合、このコード分析規則は警告なしで無効になります。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

複合語の両方の部分がスペル辞書によって認識され、目的が2つの単語を使用する場合は、この規則による警告を抑制しても安全です。

また、スペルチェック用のカスタム辞書に複合単語を追加することもできます。 カスタム辞書内の単語は、違反を発生させません。 詳細については、「[方法 :コード分析辞書](../code-quality/how-to-customize-the-code-analysis-dictionary.md)をカスタマイズします。

## <a name="related-rules"></a>関連するルール

- [CA1702複合語は、大文字と小文字が正しく区別されます。](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)
- [CA1709識別子は正しく使用する必要があります](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708識別子の大文字と小文字の区別が異なる場合](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

## <a name="see-also"></a>関連項目

- [大文字の使用規則](/dotnet/standard/design-guidelines/capitalization-conventions)
- [名前付けのガイドライン](/dotnet/standard/design-guidelines/naming-guidelines)
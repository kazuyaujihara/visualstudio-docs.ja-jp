---
title: CA1714:フラグ列挙型は、複数形の名前を含んでいなければなりません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- FlagsEnumsShouldHavePluralNames
- CA1714
helpviewer_keywords:
- CA1714
- FlagsEnumsShouldHavePluralNames
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 79585cd9cae31f46a9506085c9c8faf5b5844d44
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234090"
---
# <a name="ca1714-flags-enums-should-have-plural-names"></a>CA1714:フラグ列挙型は、複数形の名前を含んでいなければなりません

|||
|-|-|
|TypeName|FlagsEnumsShouldHavePluralNames|
|CheckId|CA1714|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

列挙体のが<xref:System.FlagsAttribute?displayProperty=fullName>で、その名前の末尾がの ' ではありません。

既定では、この規則は外部から参照できる列挙のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

で<xref:System.FlagsAttribute>マークされている型には複数形の名前があります。これは、属性が複数の値を指定できることを示すためです。 たとえば、曜日を定義する列挙体は、複数の日を指定できるアプリケーションで使用することが想定されています。 この列挙体には<xref:System.FlagsAttribute>が含まれている必要があり、' Days ' という名前を付けることができます。 1つの日だけを指定できるようにする同様の列挙には、属性は含まれず、"Day" と呼ばれることもあります。

名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェア ライブラリを習得するまでの時間を短縮でき、マネージド コード開発の専門家によってライブラリが開発されたという信頼を顧客に与えることができます。

## <a name="how-to-fix-violations"></a>違反の修正方法

列挙型の名前を複数形にすることも、複数<xref:System.FlagsAttribute>の列挙値を同時に指定しない場合は属性を削除することもできます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

名前が複数形の単語であっても、の末尾がではない場合、違反を抑制するのは安全です。 たとえば、前述の複数日間の列挙に ' DaysOfTheWeek ' という名前が付けられている場合、ルールのロジックに違反することになりますが、その目的は違反になります。 このような違反は抑制する必要があります。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1714.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (名前付け) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="related-rules"></a>関連するルール

- [CA1027FlagsAttribute で列挙をマークする](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217FlagsAttribute で列挙をマークしない](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>関連項目

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [列挙型のデザイン](/dotnet/standard/design-guidelines/enum)
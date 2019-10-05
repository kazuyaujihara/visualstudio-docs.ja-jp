---
title: CA1704:識別子は正しく入力されなければなりません
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fa04ca237134c1947b5c58b921f87f32a1ecfb16
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234290"
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704:識別子は正しく入力されなければなりません

|||
|-|-|
|TypeName|IdentifiersShouldBeSpelledCorrectly|
|CheckId|CA1704|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

識別子の名前に、Microsoft スペルチェックライブラリで認識されない1つ以上の単語が含まれています。 この規則では、コンストラクターや、get や set プロパティアクセサーなどの特別な名前のメンバーはチェックされません。

## <a name="rule-description"></a>規則の説明

このルールは、識別子をトークンに解析し、各トークンのスペルをチェックします。 解析アルゴリズムでは、次の変換が実行されます。

- 大文字は新しいトークンを開始します。 たとえば、MyNameIsJoe は、"My"、"Name"、"Is"、"Joe" になります。

- 大文字を複数使用する場合は、最後の大文字の文字によって新しいトークンが開始されます。 たとえば、"GUI"、"Editor" に GUIEditor ます。

- 先頭と末尾のアポストロフィは削除されます。 たとえば、"sender" は "sender" にトークンを送信します。

- アンダースコアはトークンの末尾を表し、削除されます。 たとえば、Hello_world は "Hello", "world" になります。

- 埋め込みアンパサンドは削除されます。 たとえば、& 台紙を "format" に設定します。

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

この規則違反を修正するには、単語のスペルを修正するか、またはカスタム辞書に単語を追加します。

### <a name="to-add-words-to-a-custom-dictionary"></a>カスタム辞書に単語を追加するには

カスタム辞書 XML ファイルに「 *Customdictionary*.xml」という名前を指定します。 ツールのインストールディレクトリ、プロジェクトディレクトリ、またはユーザーのプロファイルにあるツールに関連付けられているディレクトリ ( *%USERPROFILE%\Application Data\\...* ) に辞書を配置します。Visual Studio でカスタム辞書をプロジェクトに追加する方法については、 [「」を参照してください。コード分析辞書](../code-quality/how-to-customize-the-code-analysis-dictionary.md)をカスタマイズします。

- 辞書/単語/認識されたパスで違反が発生しないようにする単語を追加します。

- 辞書/単語/認識されないパスで違反を引き起こす可能性のある単語を追加します。

- [辞書/単語/非推奨のパス] の下で、不使用としてフラグが設定されている単語を追加します。 関連するルールのトピック[CA1726 を参照してください。詳細につい](../code-quality/ca1726-use-preferred-terms.md)ては、適切な用語を使用してください。

- 略語の大文字と小文字の規則に、辞書/頭字語/CasingExceptions パスに例外を追加します。

カスタム辞書ファイルの構造の例を次に示します。

```xml
<Dictionary>
   <Words>
      <Unrecognized>
         <Word>cb</Word>
      </Unrecognized>
      <Recognized>
         <Word>stylesheet</Word>
         <Word>GotDotNet</Word>
      </Recognized>
      <Deprecated>
         <Term PreferredAlternate="EnterpriseServices">ComPlus</Term>
      </Deprecated>
   </Words>
   <Acronyms>
      <CasingExceptions>
         <Acronym>CJK</Acronym>
         <Acronym>Pi</Acronym>
      </CasingExceptions>
   </Acronyms>
</Dictionary>
```

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則からの警告が表示されないようにするには、単語のスペルが意図的に間違っていて、その単語がライブラリの限られたセットに適用されます。 正しい綴りの単語を使用すると、新しいソフトウェアライブラリに必要な学習曲線を減らすことができます。

## <a name="related-rules"></a>関連するルール

- [CA2204リテラルは正しく入力されなければなりません](../code-quality/ca2204-literals-should-be-spelled-correctly.md)
- [CA1703リソース文字列は正しく入力されなければなりません](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1709識別子は正しく使用する必要があります](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708識別子の大文字と小文字の区別が異なる場合](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA1707識別子にアンダースコアを含めることはできません](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1726優先する用語を使用する](../code-quality/ca1726-use-preferred-terms.md)

## <a name="see-also"></a>関連項目

- [方法: コード分析辞書をカスタマイズする](../code-quality/how-to-customize-the-code-analysis-dictionary.md)」を参照してください

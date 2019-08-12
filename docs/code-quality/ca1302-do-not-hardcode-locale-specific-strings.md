---
title: CA1302:ロケール特有の文字列をハードコードしません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
helpviewer_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
ms.assetid: 05ed134a-837d-43d7-bf97-906edeac44ce
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0b3789b5e786038c2bf1fe5e823a1b0fb4f7a7c9
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922725"
---
# <a name="ca1302-do-not-hardcode-locale-specific-strings"></a>CA1302:ロケール特有の文字列をハードコードしません

|||
|-|-|
|TypeName|DoNotHardcodeLocaleSpecificStrings|
|CheckId|CA1302|
|Category|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
メソッドは、特定のシステムフォルダーのパスの一部を表す文字列リテラルを使用します。

## <a name="rule-description"></a>規則の説明
列挙<xref:System.Environment.SpecialFolder?displayProperty=fullName>には、特別なシステムフォルダーを参照するメンバーが含まれています。 これらのフォルダーの場所は、オペレーティングシステムごとに異なる値を持つことができ、ユーザーは一部の場所を変更することができ、場所はローカライズされます。 特別なフォルダーの例としては、システムフォルダーがあります。この[!INCLUDE[winxp](../code-quality/includes/winxp_md.md)]フォルダーは、では[!INCLUDE[win2kfamily](../code-quality/includes/win2kfamily_md.md)]"C:\WINDOWS\system32" になりますが、では "C:\WINNT\system32" です。 メソッド<xref:System.Environment.GetFolderPath%2A?displayProperty=fullName>は、 <xref:System.Environment.SpecialFolder>列挙体に関連付けられた場所を返します。 によって<xref:System.Environment.GetFolderPath%2A>返される場所はローカライズされ、現在実行中のコンピューターに適しています。

この規則は、 <xref:System.Environment.GetFolderPath%2A>メソッドを使用して取得されたフォルダーパスを別のディレクトリレベルにトークン化します。 各文字列リテラルは、トークンと比較されます。 一致が見つかった場合は、メソッドが、トークンに関連付けられているシステムの場所を参照する文字列を構築していることを前提としています。 移植性とローカライズ性を確保<xref:System.Environment.GetFolderPath%2A>するには、文字列リテラルを使用する代わりに、メソッドを使用して特殊なシステムフォルダーの場所を取得します。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.Environment.GetFolderPath%2A>メソッドを使用して場所を取得します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
<xref:System.Environment.SpecialFolder>列挙体に関連付けられているシステムの場所の1つを参照するために文字列リテラルが使用されていない場合は、この規則による警告を抑制しても安全です。

## <a name="example"></a>例
次の例では、common application data フォルダーのパスを構築します。これにより、このルールから3つの警告が生成されます。 次に、 <xref:System.Environment.GetFolderPath%2A>メソッドを使用してパスを取得します。

[!code-csharp[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/CSharp/ca1302-do-not-hardcode-locale-specific-strings_1.cs)]
[!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/VisualBasic/ca1302-do-not-hardcode-locale-specific-strings_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA1303ローカライズされたパラメーターとしてリテラルを渡さない](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)
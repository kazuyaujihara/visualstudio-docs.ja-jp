---
title: 'CA1302: ロケール固有の文字列をハードコーディングしない |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
helpviewer_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
ms.assetid: 05ed134a-837d-43d7-bf97-906edeac44ce
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 6e16fff154b5c0df660b06e5bf9e9e838762adff
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661475"
---
# <a name="ca1302-do-not-hardcode-locale-specific-strings"></a>CA1302: ロケール特有の文字列をハードコードしません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotHardcodeLocaleSpecificStrings|
|CheckId|CA1302|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 メソッドは、特定のシステムフォルダーのパスの一部を表す文字列リテラルを使用します。

## <a name="rule-description"></a>規則の説明
 @No__t_0 列挙には、特別なシステムフォルダーを参照するメンバーが含まれています。 これらのフォルダーの場所は、オペレーティングシステムごとに異なる値を持つことができ、ユーザーは一部の場所を変更することができ、場所はローカライズされます。 特別なフォルダーの例としては、システムフォルダー ([!INCLUDE[winxp](../includes/winxp-md.md)] では "C:\WINDOWS\system32"、[!INCLUDE[win2kfamily](../includes/win2kfamily-md.md)] では "C:\WINNT\system32" などがあります。 @No__t_0 メソッドは、<xref:System.Environment.SpecialFolder> 列挙に関連付けられた場所を返します。 @No__t_0 によって返される場所はローカライズされ、現在実行中のコンピューターに適しています。

 この規則は、<xref:System.Environment.GetFolderPath%2A> メソッドを使用して取得したフォルダーパスを別のディレクトリレベルにトークン化します。 各文字列リテラルは、トークンと比較されます。 一致が見つかった場合は、メソッドが、トークンに関連付けられているシステムの場所を参照する文字列を構築していることを前提としています。 移植性とローカライズ性を確保するには、文字列リテラルを使用する代わりに、<xref:System.Environment.GetFolderPath%2A> メソッドを使用して、特殊なシステムフォルダーの場所を取得します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.Environment.GetFolderPath%2A> メソッドを使用して場所を取得します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 文字列リテラルが <xref:System.Environment.SpecialFolder> 列挙に関連付けられているシステムの場所の1つを参照するために使用されていない場合は、この規則による警告を抑制することが安全です。

## <a name="example"></a>例
 次の例では、common application data フォルダーのパスを構築します。これにより、このルールから3つの警告が生成されます。 次に、この例では、<xref:System.Environment.GetFolderPath%2A> メソッドを使用してパスを取得します。

 [!code-csharp[FxCop.Globalization.HardcodedLocaleStrings#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.HardcodedLocaleStrings/cs/FxCop.Globalization.HardcodedLocaleStrings.cs#1)]
 [!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Globalization.HardcodedLocaleStrings/vb/FxCop.Globalization.HardcodedLocaleStrings.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1303: ローカライズされたパラメーターとしてリテラルを渡さないでください](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)

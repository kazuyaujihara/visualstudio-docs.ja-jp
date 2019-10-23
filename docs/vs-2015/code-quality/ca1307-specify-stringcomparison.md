---
title: 'CA1307: StringComparison | を指定します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 111f0b85a601d931ac17bde46f7170fa81e71815
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661398"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307: StringComparison の指定
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 文字列比較操作では、<xref:System.StringComparison> パラメーターを設定しないメソッドオーバーロードが使用されています。

## <a name="rule-description"></a>規則の説明
 多くの文字列操作 (最も重要な <xref:System.String.Compare%2A> および <xref:System.String.Equals%2A> メソッド) は、<xref:System.StringComparison> 列挙値をパラメーターとして受け取るオーバーロードを提供します。

 @No__t_0 パラメーターを受け取るオーバーロードが存在する場合は常に、このパラメーターを受け取らないオーバーロードの代わりに使用する必要があります。 このパラメーターを明示的に設定することにより、コードを明確にし、保守を容易にすることができます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、パラメーターとして <xref:System.StringComparison> 列挙を受け入れるオーバーロードに文字列比較メソッドを変更します。 例: `String.Compare(str1, str2)` を `String.Compare(str1, str2, StringComparison.Ordinal)` に変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 ライブラリまたはアプリケーションが限定されたローカルユーザーを対象としていて、ローカライズされない場合は、この規則による警告を抑制することが安全です。

## <a name="see-also"></a>参照
 [グローバリゼーションの警告](../code-quality/globalization-warnings.md) [CA1309: 序数の Stringcomparison を使用する](../code-quality/ca1309-use-ordinal-stringcomparison.md)

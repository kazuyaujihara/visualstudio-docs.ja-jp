---
title: CA1307:StringComparison の指定
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e352eea1b7fcf82cb948315affeae6e30690a4aa
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234972"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307:StringComparison の指定

|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
文字列比較操作では、パラメーターを<xref:System.StringComparison>設定しないメソッドオーバーロードが使用されています。

## <a name="rule-description"></a>規則の説明
多くの<xref:System.String.Compare%2A>文字列操作 (最も重要な<xref:System.String.Equals%2A>メソッドとメソッド) は、列挙値<xref:System.StringComparison>をパラメーターとして受け取るオーバーロードを提供します。

パラメーターを<xref:System.StringComparison>受け取るオーバーロードが存在する場合は常に、このパラメーターを受け取らないオーバーロードの代わりに使用する必要があります。 このパラメーターを明示的に設定することにより、コードを明確にし、保守を容易にすることができます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.StringComparison>列挙体をパラメーターとして受け入れるオーバーロードに文字列比較メソッドを変更します。 例: をに`String.Compare(str1, str2)` `String.Compare(str1, str2, StringComparison.Ordinal)`変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
ライブラリまたはアプリケーションが限定されたローカルユーザーを対象としていて、ローカライズされない場合は、この規則による警告を抑制することが安全です。

## <a name="see-also"></a>関連項目

- [グローバリゼーションに関する警告](../code-quality/globalization-warnings.md)
- [CA1309序数の StringComparison を使用する](../code-quality/ca1309-use-ordinal-stringcomparison.md)
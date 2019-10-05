---
title: CA1820:文字列の長さを使用して空の文字列をテストします
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b197cacc764f1f5472d3eb074ac89199db508408
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233428"
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820:文字列の長さを使用して空の文字列をテストします

|||
|-|-|
|TypeName|TestForEmptyStringsUsingStringLength|
|CheckId|CA1820|
|カテゴリ|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

文字列は、を使用<xref:System.Object.Equals%2A?displayProperty=nameWithType>して空の文字列と比較されます。

## <a name="rule-description"></a>規則の説明

プロパティ<xref:System.String.Length%2A?displayProperty=nameWithType> <xref:System.Object.Equals%2A>またはメソッドを使用した文字列の比較は、を使用するよりも高速です。 <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> これは、 <xref:System.Object.Equals%2A>が、 <xref:System.String.Length%2A>プロパティ値を取得し<xref:System.String.IsNullOrEmpty%2A>て0と比較するために実行された命令のいずれかまたはの数よりもはるかに多くの MSIL 命令を実行するためです。

Null 文字列の場合<xref:System.Object.Equals%2A>は`<string>.Length == 0` 、との動作が異なります。 Null 文字列の<xref:System.String.Length%2A>プロパティの値を取得しようとすると、共通言語ランタイムはを<xref:System.NullReferenceException?displayProperty=fullName>スローします。 Null 文字列と空の文字列の比較を実行しても、共通言語ランタイムは例外をスローせず、を`false`返します。 Null のテストは、これらの2つの方法の相対的なパフォーマンスに大きな影響を与えません。 .NET Framework 2.0 以降を対象とする場合は<xref:System.String.IsNullOrEmpty%2A> 、メソッドを使用します。 それ以外の場合<xref:System.String.Length%2A>は、可能な限り = = 0 の比較を使用します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、 <xref:System.String.IsNullOrEmpty%2A>メソッドを使用するように比較を変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

パフォーマンスが問題にならない場合は、このルールからの警告を抑制することが安全です。

## <a name="example"></a>例

次の例は、空の文字列を検索するために使用されるさまざまな手法を示しています。

[!code-csharp[FxCop.Performance.StringTest#1](../code-quality/codesnippet/CSharp/ca1820-test-for-empty-strings-using-string-length_1.cs)]
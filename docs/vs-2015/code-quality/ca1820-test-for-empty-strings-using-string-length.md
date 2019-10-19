---
title: 'CA1820: 文字列 length | を使用して空の文字列をテストします。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 6711dac907de2777cf892b20269fec7e99d3bd6f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72657501"
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: 文字列の長さを使用して空の文字列をテストします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TestForEmptyStringsUsingStringLength|
|CheckId|CA1820|
|カテゴリ|Microsoft. パフォーマンス|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 文字列は <xref:System.Object.Equals%2A?displayProperty=fullName> を使用して空の文字列と比較されます。

## <a name="rule-description"></a>規則の説明
 @No__t_0 プロパティまたは <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> メソッドを使用した文字列の比較は <xref:System.Object.Equals%2A> を使用するよりもはるかに高速です。 これは、<xref:System.Object.Equals%2A> は、<xref:System.String.IsNullOrEmpty%2A> または <xref:System.String.Length%2A> プロパティ値を取得して0と比較するために実行された命令の数よりもはるかに多くの MSIL 命令を実行するためです。

 @No__t_0 と <xref:System.String.Length%2A> = = 0 は、null 文字列に対して動作が異なることに注意してください。 Null 文字列の <xref:System.String.Length%2A> プロパティの値を取得しようとすると、共通言語ランタイムによって <xref:System.NullReferenceException?displayProperty=fullName> がスローされます。 Null 文字列と空の文字列の比較を実行しても、共通言語ランタイムは例外をスローしません。この比較では `false` が返されます。 Null のテストは、これらの2つの方法の相対的なパフォーマンスに大きな影響を与えません。 @No__t_0 を対象とする場合は、<xref:System.String.IsNullOrEmpty%2A> メソッドを使用します。 それ以外の場合は、可能な限り、<xref:System.String.Length%2A> = = を使用して比較してください。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.String.Length%2A> プロパティを使用するように比較を変更し、null 文字列をテストします。 @No__t_0 を対象とする場合は、<xref:System.String.IsNullOrEmpty%2A> メソッドを使用します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 パフォーマンスが問題にならない場合は、このルールからの警告を抑制することが安全です。

## <a name="example"></a>例
 次の例は、空の文字列を検索するために使用されるさまざまな手法を示しています。

 [!code-csharp[FxCop.Performance.StringTest#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.StringTest/cs/FxCop.Performance.StringTest.cs#1)]

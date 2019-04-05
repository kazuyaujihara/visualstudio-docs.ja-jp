---
title: CA1064:例外はパブリックである必要があります |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 00d188188f722907c2bac20e84cb9291ef8bc0fe
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "58978417"
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064:例外は public として設定する必要があります
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ExceptionsShouldBePublic|
|CheckId|CA1064|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 パブリックでない例外がから直接派生<xref:System.Exception>、 <xref:System.SystemException>、または<xref:System.ApplicationException>します。

## <a name="rule-description"></a>規則の説明
 内部例外は、独自の内部スコープ内で表示されるだけです。 内部スコープの外側にある例外は、基本例外を使用しなければキャッチできません。 場合、内部例外から継承<xref:System.Exception>、 <xref:System.SystemException>、または<xref:System.ApplicationException>、外部のコードには、例外の処理方法を把握するための十分な情報はありません。

 あるコードをさらに出力できるようになります基本例外で高度な処理を行うと考えることは、コードに後で使用される、ベースとして内部例外のパブリック例外がある場合。 パブリックの例外が T:System.Exception、T:System.SystemException、または T:System.ApplicationException によって提供されているものより多くの情報があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 例外を公開またはパブリックでない例外からの内部例外を派生<xref:System.Exception>、 <xref:System.SystemException>、または<xref:System.ApplicationException>します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールからのメッセージを抑制する場合は、常に、独自の内部スコープ内でプライベートの例外がキャッチされることを確認します。

## <a name="example"></a>例
 このルールは、例外クラスの例外から直接派生した、内部に、最初の例のメソッドで FirstCustomException に対して適用されます。 クラスは、例外から直接派生も、していますが、クラスがパブリックとして宣言されているために、ルールは、SecondCustomException クラスでは起動されません。 3 番目のクラスもは発生しません。 ルールから直接派生しないため、 <xref:System.Exception?displayProperty=fullName>、 <xref:System.SystemException?displayProperty=fullName>、または<xref:System.ApplicationException?displayProperty=fullName>します。

 [!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.design.exceptionsshouldbepublic.ca1064/cs/ca1064 - exceptionsshouldbepublic.cs#1)]

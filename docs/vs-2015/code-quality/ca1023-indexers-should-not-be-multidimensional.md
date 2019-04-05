---
title: CA1023:インデクサーを多次元することはできません |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IndexersShouldNotBeMultidimensional
- CA1023
helpviewer_keywords:
- CA1023
- IndexersShouldNotBeMultidimensional
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2b9cf9cd97dd50577a466ed4d433e0e1dbd5da4d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975081"
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023:インデクサーを多次元にすることはできません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|IndexersShouldNotBeMultidimensional|
|CheckId|CA1023|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリックまたはプロテクト型には、1 つ以上のインデックスを使用するパブリックまたはプロテクトのインデクサーが含まれています。

## <a name="rule-description"></a>規則の説明
 インデクサー、つまり、インデックス付きプロパティには、1 つのインデックスを使用する必要があります。 多次元のインデクサーでは、ライブラリの使いやすさを大幅に短縮できます。 デザインは、複数のインデックスを必要とする場合は、型は、論理データ ストアを表すかどうかを再確認します。 それ以外の場合は、メソッドを使用します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、唯一の整数または文字列のインデックスを使用してデザインを変更またはインデクサーではなく、メソッドを使用します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 非標準のインデクサーの必要性を慎重に検討した後にのみこの規則による警告を抑制します。

## <a name="example"></a>例
 次の例は、型`DayOfWeek03`規則に違反する多次元のインデクサーを使用します。 インデクサーは変換の種類として見なすことができ、そのため、メソッドとして公開がより適切にします。 型がで再設計されました`RedesignedDayOfWeek03`ルールを満たすためにします。

 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.OneDimensionForIndexer/cpp/FxCop.Design.OneDimensionForIndexer.cpp#1)]
 [!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.OneDimensionForIndexer/cs/FxCop.Design.OneDimensionForIndexer.cs#1)]
 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.OneDimensionForIndexer/vb/FxCop.Design.OneDimensionForIndexer.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA 1043:インデクサーは整数または文字列引数を使用して、](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)

 [CA 1024:適切な場所のプロパティを使用します。](../code-quality/ca1024-use-properties-where-appropriate.md)

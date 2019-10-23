---
title: 'CA1043: インデクサーに整数または文字列引数を使用する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 528b3a1f301544ccb20cfa6bddc31c0a5c50d1ca
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668302"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: インデクサーには整数または文字列引数を使用します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリック型またはプロテクト型に、<xref:System.Int32?displayProperty=fullName>、<xref:System.Int64?displayProperty=fullName>、<xref:System.Object?displayProperty=fullName>、または <xref:System.String?displayProperty=fullName> 以外のインデックスの種類を使用するパブリックインデクサーまたは保護されたインデクサーが含まれています。

## <a name="rule-description"></a>規則の説明
 インデクサー (インデックス付きプロパティ) では、インデックスに整数または文字列型を使用する必要があります。 これらの型は、通常、データ構造のインデックスを作成し、ライブラリの使いやすさを向上させるために使用されます。 @No__t_0 型の使用は、デザイン時に特定の整数または文字列型を指定できない場合に制限する必要があります。 この設計でインデックスに他の型が必要な場合は、型が論理データストアを表すかどうかを再検討してください。 論理データストアを表していない場合は、メソッドを使用します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、インデックスを整数または文字列型に変更するか、インデクサーではなくメソッドを使用します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 非標準のインデクサーの必要性を慎重に検討した後にのみ、この規則からの警告を非表示にします。

## <a name="example"></a>例
 次の例は、<xref:System.Int32> インデックスを使用するインデクサーを示しています。

 [!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers/cpp/FxCop.Design.IntegralOrStringIndexers.cpp#1)]
 [!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers/cs/FxCop.Design.IntegralOrStringIndexers.cs#1)]
 [!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers/vb/FxCop.Design.IntegralOrStringIndexers.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1023: インデクサーを多次元にすることはできません](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)

 [CA1024: 適切な場所にプロパティを使用します](../code-quality/ca1024-use-properties-where-appropriate.md)

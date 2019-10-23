---
title: 'CA1052: スタティックホルダー型はシールドされている必要があります |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldBeSealed
- CA1052
helpviewer_keywords:
- CA1052
- StaticHolderTypesShouldBeSealed
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 75498be48e5ed4e723a95c5193001720db878458
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668886"
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052: スタティック ホルダー型はシールされていなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|StaticHolderTypesShouldBeSealed|
|CheckId|CA1052|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリックまたはプロテクト型には静的メンバーのみが含まれており、 [sealed](https://msdn.microsoft.com/library/8e4ed5d3-10be-47db-9488-0da2008e6f3f) ([NotInheritable](https://msdn.microsoft.com/library/5c4da7c9-9562-4653-a947-1972e992f9f9)) 修飾子で宣言されていません。

## <a name="rule-description"></a>規則の説明
 この規則では、静的メンバーのみを含む型が継承されるように設計されていないことを前提としています。これは、派生型でオーバーライドできる機能が型に用意されていないためです。 継承を意図していない型は、基本型としての使用を禁止するために、`sealed` 修飾子でマークする必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、型を `sealed` としてマークします。 @No__t_0 2.0 以前のバージョンを対象としている場合は、型を `static` としてマークする方法が適しています。 このようにして、プライベートコンストラクターを宣言しなくても、クラスが作成されないようにすることができます。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 型が継承されるように設計されている場合にのみ、この規則からの警告を非表示にします。 @No__t_0 修飾子がない場合は、型が基本型として有用であることが示されます。

## <a name="example-of-a-violation"></a>違反の例

### <a name="description"></a>説明
 次の例は、規則に違反する型を示しています。

### <a name="code"></a>コード
 [!code-cpp[FxCop.Design.StaticMembers#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.StaticMembers/cpp/FxCop.Design.StaticMembers.cpp#1)]
 [!code-csharp[FxCop.Design.StaticMembers#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.StaticMembers/cs/FxCop.Design.StaticMembers.cs#1)]
 [!code-vb[FxCop.Design.StaticMembers#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.StaticMembers/vb/FxCop.Design.StaticMembers.vb#1)]

## <a name="fix-with-the-static-modifier"></a>Static 修飾子を使用して修正します。

### <a name="description"></a>説明
 次の例では、型を `static` 修飾子でマークして、この規則違反を修正する方法を示します。

### <a name="code"></a>コード
 [!code-csharp[FxCop.Design.StaticMembersFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.StaticMembersFixed/cs/FxCop.Design.StaticMembersFixed.cs#1)]

## <a name="related-rules"></a>関連規則
 [CA1053: スタティック ホルダー型にはコンストラクターを含めません](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)

---
title: 'CA1036: 比較可能な型のメソッドをオーバーライドします |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1036
- OverrideMethodsOnComparableTypes
helpviewer_keywords:
- OverrideMethodsOnComparableTypes
- CA1036
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 779e6258f9c5be256a7973a5d917045507fc82e6
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661823"
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036: 比較可能な型でメソッドをオーバーライドします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OverrideMethodsOnComparableTypes|
|CheckId|CA1036|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 パブリック型またはプロテクト型が <xref:System.IComparable?displayProperty=fullName> インターフェイスを実装しており、<xref:System.Object.Equals%2A?displayProperty=fullName> をオーバーライドしていないか、または言語固有の演算子の等値、不等号、未満、またはより大きい値をオーバーロードしていません。 型がインターフェイスの実装のみを継承する場合、規則は違反を報告しません。

## <a name="rule-description"></a>規則の説明
 カスタム並べ替え順序を定義する型は、<xref:System.IComparable> インターフェイスを実装します。 @No__t_0 メソッドは、型の2つのインスタンスの正しい並べ替え順序を示す整数値を返します。 このルールは、並べ替え順序を設定する型を識別します。これは、等値、非等値、より小さい、およびより大きいという通常の意味が適用されないことを意味します。 @No__t_0 の実装を指定する場合は、通常、<xref:System.IComparable.CompareTo%2A> と一貫性のある値を返すように <xref:System.Object.Equals%2A> もオーバーライドする必要があります。 @No__t_0 をオーバーライドし、演算子のオーバーロードをサポートする言語でコーディングする場合は、<xref:System.Object.Equals%2A> と一貫性のある演算子も指定する必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則の違反を修正するには、<xref:System.Object.Equals%2A> をオーバーライドします。 プログラミング言語で演算子のオーバーロードがサポートされている場合は、次の演算子を指定します。

- op_Equality

- op_Inequality

- op_LessThan

- op_GreaterThan

  でC#は、これらの演算子を表すために使用されるトークンは、= =、! =、\<、> のようになります。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 演算子が不足していることが原因で違反が発生し、プログラミング言語で演算子のオーバーロードがサポートされていない場合に、この規則からの警告を抑制するのは安全です。これは Visual Basic .NET の場合と同様です。 また、演算子の実装がアプリケーションコンテキストで意味を持たないと判断した場合、op_Equality 以外の等値演算子でこの規則を使用した場合の警告を抑制することも安全です。 ただし、Object.equals をオーバーライドする場合は、常に op_Equality と = = 演算子を使用する必要があります。

## <a name="example"></a>例
 次の例には、<xref:System.IComparable> を正しく実装する型が含まれています。 コードコメントは、<xref:System.Object.Equals%2A> および <xref:System.IComparable> インターフェイスに関連するさまざまなルールを満たすメソッドを識別します。

 [!code-csharp[FxCop.Design.IComparable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.IComparable/cs/FxCop.Design.IComparable.cs#1)]

## <a name="example"></a>例
 次のアプリケーションは、前に示した <xref:System.IComparable> 実装の動作をテストします。

 [!code-csharp[FxCop.Design.TestIComparable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestIComparable/cs/FxCop.Design.TestIComparable.cs#1)]

## <a name="see-also"></a>参照
 <xref:System.IComparable?displayProperty=fullName> <xref:System.Object.Equals%2A?displayProperty=fullName>
 [等値演算子](https://msdn.microsoft.com/library/bc496a91-fefb-4ce0-ab4c-61f09964119a)

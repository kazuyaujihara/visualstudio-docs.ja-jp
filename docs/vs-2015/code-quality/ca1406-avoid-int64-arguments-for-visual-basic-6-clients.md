---
title: 'CA1406: Visual Basic 6 クライアントに対して Int64 引数を使用しません。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
helpviewer_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: c20ea7bd7bba6f221395c7e2c21d6c1dcc241fb4
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661298"
---
# <a name="ca1406-avoid-int64-arguments-for-visual-basic-6-clients"></a>CA1406: Visual Basic 6 クライアントに対しては Int64 引数を使用しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidInt64ArgumentsForVB6Clients|
|CheckId|CA1406|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 コンポーネントオブジェクトモデル (COM) に対して表示されるように明示的にマークされている型は、<xref:System.Int64?displayProperty=fullName> 引数を受け取るメンバーを宣言します。

## <a name="rule-description"></a>規則の説明
 Visual Basic 6 の COM クライアントは、64ビットの整数にアクセスできません。

 既定では、アセンブリ、パブリック型、パブリック型のパブリックインスタンスメンバー、およびパブリック値型のすべてのメンバーに対して、COM から参照できます。 ただし、偽陽性を減らすために、このルールでは、型の COM 参照可能範囲が明示的に指定されている必要があります。含んでいるアセンブリは `false` に設定された <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> でマークする必要があり、型は `true` に設定された <xref:System.Runtime.InteropServices.ComVisibleAttribute> でマークする必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 値を常に32ビット整数として表すことができるパラメーターのこの規則違反を修正するには、パラメーターの型を <xref:System.Int32?displayProperty=fullName> に変更します。 パラメーターの値が32ビット整数として表現できるよりも大きい場合は、パラメーターの型を <xref:System.Decimal?displayProperty=fullName> に変更します。 @No__t_0 と <xref:System.Double?displayProperty=fullName> の両方で、<xref:System.Int64> データ型の上限の範囲の有効桁数が失われることに注意してください。 メンバーが COM から参照可能でない場合は、`false` に設定された <xref:System.Runtime.InteropServices.ComVisibleAttribute> でマークします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 Visual Basic 6 の COM クライアントが型にアクセスしないことがわかっている場合は、この規則による警告を抑制しても安全です。

## <a name="example"></a>例
 次の例は、規則に違反する型を示しています。

 [!code-csharp[FxCop.Interoperability.LongArgument#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LongArgument/cs/FxCop.Interoperability.LongArgument.cs#1)]
 [!code-vb[FxCop.Interoperability.LongArgument#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LongArgument/vb/FxCop.Interoperability.LongArgument.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1413: Com 参照可能な値型ではパブリックでないフィールドを使用しません](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407: Com 参照可能な型で静的メンバーを使用しません](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: アセンブリに ComVisibleAttribute を設定します](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>参照
 [アンマネージコードの](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258) [Long データ型](https://msdn.microsoft.com/library/b4770c34-1804-4f8c-b512-c10b0893e516)との相互運用

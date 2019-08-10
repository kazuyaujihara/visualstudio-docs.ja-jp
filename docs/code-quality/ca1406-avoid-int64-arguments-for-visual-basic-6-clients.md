---
title: CA1406:Visual Basic 6 クライアントに対しては Int64 引数を使用しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
helpviewer_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 4dfcc612e931756b0e3d817556c9b37844bc3cfd
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922039"
---
# <a name="ca1406-avoid-int64-arguments-for-visual-basic-6-clients"></a>CA1406:Visual Basic 6 クライアントに対しては Int64 引数を使用しません

|||
|-|-|
|TypeName|AvoidInt64ArgumentsForVB6Clients|
|CheckId|CA1406|
|Category|Microsoft. 相互運用性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
コンポーネントオブジェクトモデル (COM) に対して表示されるように明示的にマークされて<xref:System.Int64?displayProperty=fullName>いる型は、引数を受け取るメンバーを宣言します。

## <a name="rule-description"></a>規則の説明
Visual Basic 6 COM クライアントは、64 ビット整数値にアクセスできません。

既定では、アセンブリ、パブリック型、パブリック型のパブリックインスタンスメンバー、およびパブリック値型のすべてのメンバーに対して、COM から参照できます。 ただし、偽陽性を減らすために、このルールでは、型の COM 参照可能範囲が明示的に指定されている必要があります。含んでいる<xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>アセンブリは、がに`false`設定されたでマークされ、型<xref:System.Runtime.InteropServices.ComVisibleAttribute>はに`true`設定されたでマークされる必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
値を常に32ビット整数として表すことができるパラメーターのこの規則違反を修正するには、パラメーターの型<xref:System.Int32?displayProperty=fullName>をに変更します。 パラメーターの値が32ビットの整数として表すことができる値よりも大きい場合は、パラメーターの型<xref:System.Decimal?displayProperty=fullName>をに変更します。 と<xref:System.Single?displayProperty=fullName> <xref:System.Int64>の両方で、データ型の上限の範囲の有効桁数が失われることに注意してください。 <xref:System.Double?displayProperty=fullName> メンバーが COM から参照できるようになっていない場合は、を<xref:System.Runtime.InteropServices.ComVisibleAttribute>に`false`設定してマークします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
Visual Basic 6 の COM クライアントが型にアクセスしないことがわかっている場合は、この規則による警告を抑制しても安全です。

## <a name="example"></a>例
次の例は、規則に違反する型を示しています。

[!code-csharp[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/CSharp/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.cs)]
[!code-vb[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/VisualBasic/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA1413COM 参照可能な値型ではパブリックでないフィールドを避けてください](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

[CA1407COM 参照可能な型で静的メンバーを避けます](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

[CA1017アセンブリを ComVisibleAttribute にマークします](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>関連項目

- [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)
- [Long データ型](/dotnet/visual-basic/language-reference/data-types/long-data-type)
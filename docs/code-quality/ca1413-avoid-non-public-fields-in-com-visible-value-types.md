---
title: CA1413:Com 参照可能な値型ではパブリックでないフィールドを使用しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
helpviewer_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
ms.assetid: 1352e7eb-fefc-4239-8847-25edc7804a54
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0d4fed5b16120ec069eaa4101670c88ad8f3a247
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234646"
---
# <a name="ca1413-avoid-non-public-fields-in-com-visible-value-types"></a>CA1413:Com 参照可能な値型ではパブリックでないフィールドを使用しません

|||
|-|-|
|TypeName|AvoidNonpublicFieldsInComVisibleValueTypes|
|CheckId|CA1413|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
コンポーネントオブジェクトモデル (COM) に対して表示されるように明示的にマークされた値型は、非パブリックインスタンスフィールドを宣言します。

## <a name="rule-description"></a>規則の説明
COM から参照できる値型の非パブリック インスタンス フィールドは、COM クライアントで表示できます。 フィールドの内容を確認して、公開されない情報や意図しないデザインまたはセキュリティ上の影響を与えます。

既定では、すべてのパブリック値の型は COM から参照できます。 ただし、偽陽性を減らすために、このルールでは、型の COM 参照可能範囲が明示的に指定されている必要があります。 含んでいる<xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>アセンブリは、がに`false`設定されたでマークされ、型<xref:System.Runtime.InteropServices.ComVisibleAttribute>はに`true`設定されたでマークされる必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則の違反を修正し、フィールドを非表示のままにするには、値の型を参照<xref:System.Runtime.InteropServices.ComVisibleAttribute>型に変更するか、型から属性を削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
フィールドの公開が許容される場合は、この規則による警告を抑制しても安全です。

## <a name="example"></a>例
次の例は、規則に違反する型を示しています。

[!code-csharp[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/CSharp/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.cs)]
[!code-vb[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/VisualBasic/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA1407COM 参照可能な型で静的メンバーを避けます](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

[CA1017アセンブリを ComVisibleAttribute にマークします](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>関連項目

- [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)
- [要件 (相互運用のための .NET 型の)](/dotnet/framework/interop/qualifying-net-types-for-interoperation)
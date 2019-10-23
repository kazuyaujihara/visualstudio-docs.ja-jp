---
title: 'CA1413: COM 参照可能な値型ではパブリックでないフィールドを避けてください。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
helpviewer_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
ms.assetid: 1352e7eb-fefc-4239-8847-25edc7804a54
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 7d66c2c52b6ee7f7d1d2fbbd461ca8c1251ce13d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652700"
---
# <a name="ca1413-avoid-non-public-fields-in-com-visible-value-types"></a>CA1413: Com 参照可能な値型ではパブリックでないフィールドを使用しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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

 既定では、すべてのパブリック値の型は COM から参照できます。 ただし、偽陽性を減らすために、このルールでは、型の COM 参照可能範囲が明示的に指定されている必要があります。 含んでいるアセンブリは `false` に設定された <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> でマークする必要があり、型は `true` に設定された <xref:System.Runtime.InteropServices.ComVisibleAttribute> でマークする必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則の違反を修正し、フィールドを非表示のままにするには、値の型を参照型に変更するか、型から <xref:System.Runtime.InteropServices.ComVisibleAttribute> 属性を削除します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 フィールドの公開が許容される場合は、この規則による警告を抑制しても安全です。

## <a name="example"></a>例
 次の例は、規則に違反する型を示しています。

 [!code-csharp[FxCop.Interoperability.NonpublicField#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.NonpublicField/cs/FxCop.Interoperability.NonpublicField.cs#1)]
 [!code-vb[FxCop.Interoperability.NonpublicField#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.NonpublicField/vb/FxCop.Interoperability.NonpublicField.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1407: Com 参照可能な型で静的メンバーを使用しません](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: アセンブリに ComVisibleAttribute を設定します](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>参照
 [相互運用のための .Net 型を満たす](https://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)[アンマネージコードとの相互運用](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)

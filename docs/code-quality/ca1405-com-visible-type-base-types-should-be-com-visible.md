---
title: CA1405:COM 参照可能な型の基本型は COM 参照可能でなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8e4e5c4ed258bcc88fedbb6d015fed576d326a0f
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234956"
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405:COM 参照可能な型の基本型は COM 参照可能でなければなりません

|||
|-|-|
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|
|CheckId|CA1405|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|依存関係 Sonfix|

## <a name="cause"></a>原因
コンポーネントオブジェクトモデル (COM) で参照できる型が COM 参照可能ではない型から派生しています。

## <a name="rule-description"></a>規則の説明
COM 参照可能な型が新しいバージョンのメンバーを追加する場合、現在のバージョンにバインドされている COM クライアントの互換性を回避するために、厳密なガイドラインに従う必要があります。 COM で参照できない型は、新しいメンバーを追加するときに、これらの COM バージョン管理規則に従う必要がないということを前提としています。 ただし、com 参照可能な型が com 不可視型から派生し、または<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> <xref:System.Runtime.InteropServices.ClassInterfaceType> (既定値) のクラスインターフェイスを公開する場合は、基本型のすべてのパブリックメンバー (冗長であるとして明示的に com 非表示に設定されている場合を除く)は COM に公開されます。 基本型が後続のバージョンで新しいメンバーを追加する場合、派生型のクラスインターフェイスにバインドされているすべての COM クライアントが破損する可能性があります。 Com 参照可能な型は、com クライアントを中断する可能性を減らすために、com 参照可能な型からのみ派生しなければなりません。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、基本型 COM を参照できるようにするか、派生型 COM を非表示にします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、規則に違反する型を示しています。

[!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
[!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]

## <a name="see-also"></a>関連項目

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName>
- [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)
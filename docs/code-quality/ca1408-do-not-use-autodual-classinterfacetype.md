---
title: CA1408:AutoDual ClassInterfaceType を使用しないでください
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotUseAutoDualClassInterfaceType
- CA1408
helpviewer_keywords:
- CA1408
- DoNotUseAutoDualClassInterfaceType
ms.assetid: 60ca5e02-3c51-42dd-942b-4f950eecfa0f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b79483e8703ea297634d0d81d5449c09b58c9fb7
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921985"
---
# <a name="ca1408-do-not-use-autodual-classinterfacetype"></a>CA1408:AutoDual ClassInterfaceType を使用しないでください

|||
|-|-|
|TypeName|DoNotUseAutoDualClassInterfaceType|
|CheckId|CA1408|
|Category|Microsoft. 相互運用性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
コンポーネントオブジェクトモデル (COM) で参照できる型は、の<xref:System.Runtime.InteropServices.ClassInterfaceAttribute> `AutoDual` <xref:System.Runtime.InteropServices.ClassInterfaceType>値に設定された属性でマークされます。

## <a name="rule-description"></a>規則の説明
デュアル インターフェイスを使用する型を使用することで、クライアントを特定のインターフェイス レイアウトに対応付けることができます。 将来のバージョンで、この型またはその基本型のレイアウトに変更が加えられると、インターフェイスに対応付けられた COM クライアントが切り離されます。 既定では、 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>属性が指定されていない場合、ディスパッチ専用インターフェイスが使用されます。

特に指定されていない限り、パブリックなすべての非ジェネリック型は COM から参照できます。非パブリック型とジェネリック型はすべて、COM から見えません。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>属性の値`None`をの<xref:System.Runtime.InteropServices.ClassInterfaceType>値に変更し、インターフェイスを明示的に定義します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
型とその基本型のレイアウトが将来のバージョンで変更されないことが確実である場合を除き、この規則からの警告を抑制しないでください。

## <a name="example"></a>例
次の例は、規則に違反するクラスと、明示的なインターフェイスを使用するクラスの再宣言を示しています。

[!code-csharp[FxCop.Interoperability.AutoDual#1](../code-quality/codesnippet/CSharp/ca1408-do-not-use-autodual-classinterfacetype_1.cs)]
[!code-vb[FxCop.Interoperability.AutoDual#1](../code-quality/codesnippet/VisualBasic/ca1408-do-not-use-autodual-classinterfacetype_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA1403自動レイアウトの型を COM 参照可能にすることはできません](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)

[CA1412ComSource インターフェイスを IDispatch としてマークします](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)

## <a name="see-also"></a>関連項目

- [要件 (相互運用のための .NET 型の)](/dotnet/framework/interop/qualifying-net-types-for-interoperation)
- [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)
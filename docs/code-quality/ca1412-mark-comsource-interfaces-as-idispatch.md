---
title: CA1412:ComSource インターフェイスを IDispatch として設定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MarkComSourceInterfacesAsIDispatch
- CA1412
helpviewer_keywords:
- CA1412
- MarkComSourceInterfacesAsIDispatch
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: caaae787d5e4801f3fc3b8d881b386595fb2eca4
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234687"
---
# <a name="ca1412-mark-comsource-interfaces-as-idispatch"></a>CA1412:ComSource インターフェイスを IDispatch として設定します

|||
|-|-|
|TypeName|MarkComSourceInterfacesAsIDispatch|
|CheckId|CA1412|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型が<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>属性でマークされており、少なくとも1つの指定されたインターフェイスが`InterfaceIsDispatch` 、値に設定された<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>属性でマークされていません。

## <a name="rule-description"></a>規則の説明

<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>は、クラスがコンポーネントオブジェクトモデル (COM) クライアントに公開するイベントインターフェイスを識別するために使用されます。 Visual Basic 6 の COM クライアントが`InterfaceIsIDispatch`イベント通知を受信できるようにするには、これらのインターフェイスをとして公開する必要があります。 既定では、インターフェイスが<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>属性でマークされていない場合は、デュアルインターフェイスとして公開されます。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、属性を<xref:System.Runtime.InteropServices.InterfaceTypeAttribute> <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>使用して指定されているすべてのインターフェイスの値が cominterfacetype.interfaceisidispatch に設定されるように、属性を追加または変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。

## <a name="example"></a>例

次の例は、いずれかのインターフェイスが規則に違反しているクラスを示しています。

[!code-csharp[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/CSharp/ca1412-mark-comsource-interfaces-as-idispatch_1.cs)]
[!code-vb[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/VisualBasic/ca1412-mark-comsource-interfaces-as-idispatch_1.vb)]

## <a name="related-rules"></a>関連するルール

[CA1408AutoDual ClassInterfaceType を使用しない](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>関連項目

- [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)
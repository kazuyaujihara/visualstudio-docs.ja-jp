---
title: Value (XAttribute 動的プロパティ)
ms.date: 11/04/2016
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fe9127d4a7c691c34f15d399bd32f5e48cc6f0ed
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62892821"
---
# <a name="value-xattribute-dynamic-property"></a>Value (XAttribute 動的プロパティ)

XML 属性の値を取得または設定します。

## <a name="syntax"></a>構文

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a>プロパティ値/戻り値

この属性の値を表す <xref:System.String> です。

## <a name="exceptions"></a>例外

|例外の種類|条件|
| - |---------------|
|<xref:System.ArgumentNullException>|設定時に `value` が `null` である場合に発生します。|

## <a name="remarks"></a>解説

このプロパティは、<xref:System.Xml.Linq.XAttribute.Value%2A> クラスの <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> プロパティに相当します。ただし、この動的プロパティは変更通知もサポートします。

## <a name="see-also"></a>関連項目

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [XAttribute クラスの動的プロパティ](../designers/xattribute-class-dynamic-properties.md)
- [属性](../designers/attribute-xelement-dynamic-property.md)
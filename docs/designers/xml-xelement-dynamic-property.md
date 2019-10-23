---
title: XML (XElement 動的プロパティ)
ms.date: 11/04/2016
ms.topic: reference
apiname:
- XElement.Xml
ms.assetid: 69ab2a33-4fe7-4cfa-97f8-eaf063decb18
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c93aaf3b43a930fe88020738460ec131972a205a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72633518"
---
# <a name="xml-xelement-dynamic-property"></a>Xml (XElement 動的プロパティ)

要素について、書式設定されていない XML コンテンツを取得します。

## <a name="syntax"></a>構文

```xaml
elem.Xml
```

## <a name="property-valuereturn-value"></a>プロパティ値/戻り値

要素に関する書式設定されていない XML コンテンツを表す <xref:System.String>。

## <a name="remarks"></a>解説

このプロパティは、<xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> パラメーターが <xref:System.Xml.Linq.XNode?displayProperty=fullName> に設定されている、`SaveOptions` クラスの <xref:System.Xml.Linq.SaveOptions> メソッドに相当します。

## <a name="see-also"></a>関連項目

- [XElement クラスの動的プロパティ](../designers/attribute-xelement-dynamic-property.md)
- [[値]](../designers/value-xelement-dynamic-property.md)
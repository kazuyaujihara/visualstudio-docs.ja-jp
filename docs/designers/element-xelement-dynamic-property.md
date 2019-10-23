---
title: Element (XElement 動的プロパティ)
ms.date: 11/04/2016
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 08b2f7f008c1522c5f65b5ee7a58c3ed98e8a845
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72637331"
---
# <a name="element-xelement-dynamic-property"></a>Element (XElement 動的プロパティ)

指定された展開名に対応する子要素のインスタンスを取得するためのインデクサーを取得します。

## <a name="syntax"></a>構文

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>プロパティ値/戻り値

`XElement Item(String expandedName)` 型のインデクサー。 このインデクサーは、展開名のパラメーターを取得し、対応する <xref:System.Xml.Linq.XElement> を返します。指定された名前を持つ要素がない場合は、`null` を返します。

## <a name="remarks"></a>解説

このプロパティは、<xref:System.Xml.Linq.XContainer.Element%2A> クラスの <xref:System.Xml.Linq.XContainer?displayProperty=fullName> メソッドに相当します。

## <a name="see-also"></a>関連項目

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [XElement クラスの動的プロパティ](../designers/attribute-xelement-dynamic-property.md)
- [要素](../designers/elements-xelement-dynamic-property.md)
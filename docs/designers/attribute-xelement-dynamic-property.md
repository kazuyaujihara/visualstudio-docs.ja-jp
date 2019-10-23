---
title: Attribute (XElement 動的プロパティ)
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0d7fc1aa0419863e933bdc0a828455fcda8671fc
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72637392"
---
# <a name="attribute-xelement-dynamic-property"></a>Attribute (XElement 動的プロパティ)

指定された展開名に対応する属性のインスタンスの取得に使用するインデクサーを取得します。

## <a name="syntax"></a>構文

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a>プロパティ値/戻り値

`XAttribute Item(String expandedName)` 型のインデクサー。 このインデクサーは、指定された属性の展開名を受け取り、対応する <xref:System.Xml.Linq.XAttribute> を返します。指定された名前を持つ属性がない場合は、`null` を返します。

## <a name="remarks"></a>解説

このプロパティは、<xref:System.Xml.Linq.XElement.Attribute%2A> クラスの <xref:System.Xml.Linq.XElement?displayProperty=fullName> メソッドに相当します。

## <a name="see-also"></a>関連項目

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [XElement クラスの動的プロパティ](../designers/attribute-xelement-dynamic-property.md)
- [[値]](../designers/value-xattribute-dynamic-property.md)
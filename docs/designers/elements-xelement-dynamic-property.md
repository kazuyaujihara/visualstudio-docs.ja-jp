---
title: Elements (XElement 動的プロパティ)
ms.date: 11/04/2016
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4ff2071ba71d60db87332b0e23948d63ac1b2289
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62845562"
---
# <a name="elements-xelement-dynamic-property"></a>Elements (XElement 動的プロパティ)

現在の要素の子要素のうち指定された拡張名に一致する子要素の取得に使用するインデクサーを取得します。

## <a name="syntax"></a>構文

```xaml
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>プロパティ値/戻り値

`IEnumerable<XElement> Item(String expandedName)` 型のインデクサー。 このインデクサーは、目的の子要素の拡張名を取得し、<xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` コレクション内の一致する子要素を返します。

## <a name="remarks"></a>解説

このプロパティは、<xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> クラスの <xref:System.Xml.Linq.XContainer> メソッドに相当します。

返されるコレクション内の要素は、XML ソース ドキュメント順になります。

このプロパティは、遅延実行を使用します。

## <a name="see-also"></a>関連項目

- [XElement クラスの動的プロパティ](../designers/xelement-class-dynamic-properties.md)
- [要素](../designers/element-xelement-dynamic-property.md)
- [子孫](../designers/descendants-xelement-dynamic-property.md)
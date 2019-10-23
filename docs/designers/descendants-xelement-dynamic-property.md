---
title: Descendants (XElement 動的プロパティ)
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fab6b90489624955ddd567492d12f54d8de2686f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72637341"
---
# <a name="descendants-xelement-dynamic-property"></a>Descendants (XElement 動的プロパティ)

現在の要素の子孫要素のうち指定された拡張名に一致するすべての子孫要素を取得するためのインデクサーを取得します。

## <a name="syntax"></a>構文

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>プロパティ値/戻り値

`IEnumerable<XElement> Item(String expandedName)` 型のインデクサー。 このインデクサーは、指定された子孫要素の拡張名を受け取り、<xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` コレクション内の一致する子要素を返します。

## <a name="remarks"></a>解説

このプロパティは、<xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> クラスの <xref:System.Xml.Linq.XContainer> メソッドに相当します。

返されるコレクション内の要素は、XML ソース ドキュメント順になります。

このプロパティは、遅延実行を使用します。

## <a name="see-also"></a>関連項目

- [XElement クラスの動的プロパティ](../designers/attribute-xelement-dynamic-property.md)
- [要素](../designers/elements-xelement-dynamic-property.md)
---
title: ExtensionDataItem 要素 |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ExtensionDataItem element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 969c82152c1e781da83fe4da20e49fdcf8dda375
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56617055"
---
# <a name="extensiondataitem-element"></a>ExtensionDataItem 要素
  キー/値の形式で、SharePoint プロジェクト アイテムに関連付けられているカスタム データ項目を指定します。 キーと値の両方には、文字列がある場合があります。

## <a name="syntax"></a>構文

```xml
<ExtensionDataItem Key = "Key of the data item"
    Value = "Value of the data item" />
```

## <a name="attributes-and-elements"></a>属性と要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

|属性|説明|
|---------------|-----------------|
|**Key**|必要な**xs: 文字列**属性。<br /><br /> このキーは、格納およびデータ項目を取得するために使用します。|
|**[値]**|必要な**xs:string**属性。<br /><br /> データ項目の値。|

### <a name="child-elements"></a>子要素
 なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ExtensionData](../sharepoint/extensiondata-element.md)|SharePoint プロジェクト アイテムに関連付けられているカスタム データ項目のコレクションを表します。|

## <a name="remarks"></a>Remarks
 関連付けるとカスタム データを SharePoint プロジェクト項目を使用して、<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A>のプロパティ、<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem>オブジェクト、Visual Studio を新しいデータを保存する**ExtensionDataItem**内の要素、`.spdata`ファイルをプロジェクト項目。 詳細については、次を参照してください。 [SharePoint プロジェクト システムの拡張機能でデータを保存](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)します。

## <a name="element-information"></a>要素情報

|||
|-|-|
|**Namespace**|http<nolink>://schemas.microsoft.com/VisualStudio/<br>SharePointProjectItemModel SharePointTools/2010/|
|**スキーマ名**|SharePoint プロジェクト項目のスキーマ|
|**ファイルの検証**|ProjectItemModelSchema.xsd|
|**空にすることができます。**|いいえ|

## <a name="see-also"></a>関連項目
- [SharePoint プロジェクト項目スキーマのリファレンス](../sharepoint/sharepoint-project-item-schema-reference.md)

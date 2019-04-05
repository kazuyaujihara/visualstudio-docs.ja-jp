---
title: FeatureProperty 要素 |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperty element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 20d24192d8613a4f41d9cdfc04371fb9c9d02076
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58322771"
---
# <a name="featureproperty-element"></a>FeatureProperty 要素
  SharePoint に配置されるときに、機能に含まれているカスタム プロパティを表します。 フィーチャーが配置されると、コードでプロパティにアクセスすることができます。

## <a name="syntax"></a>構文

```xml
<FeatureProperty Key = "Key of the property value"
    Value = "Property value" />
```

## <a name="attributes-and-elements"></a>属性と要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

|属性|説明|
|---------------|-----------------|
|**Key**|必要な**xs:string**属性。<br /><br /> このキーは、格納およびプロパティの値を取得するために使用します。 各プロパティが、機能内で一意キーが必要です。|
|**[値]**|必要な**xs:string**属性。<br /><br /> プロパティ値。|

### <a name="child-elements"></a>子要素
 なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[FeatureProperties](../sharepoint/featureproperties-element.md)|SharePoint に配置されるときに、機能に含まれているプロパティ値のコレクションを表します。|

## <a name="remarks"></a>Remarks
 機能プロパティの詳細については、[プロジェクト項目でのパッケージと展開の情報を提供する](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)を参照してください。

## <a name="element-information"></a>要素情報

|||
|-|-|
|**Namespace**|http:\/\/schemas.microsoft.com/VisualStudio/<br>SharePointProjectItemModel SharePointTools/2010/|
|**スキーマ名**|SharePoint プロジェクト項目のスキーマ|
|**ファイルの検証**|ProjectItemModelSchema.xsd|
|**空にすることができます。**|いいえ|

## <a name="see-also"></a>関連項目
- [SharePoint プロジェクト項目スキーマのリファレンス](../sharepoint/sharepoint-project-item-schema-reference.md)
- [プロジェクト項目でパッケージ化と配置の情報を提供します。](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)

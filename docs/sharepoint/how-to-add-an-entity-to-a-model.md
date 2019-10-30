---
title: '方法: モデルにエンティティを追加する |Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- EntityTool
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], entity
- Business Data Connectivity service [SharePoint development in Visual Studio], adding an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], entity
- BDC [SharePoint development in Visual Studio], adding an entity
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b1a7ec1eab5cdcf2e415a4803c51c9da91be29c9
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72985240"
---
# <a name="how-to-add-an-entity-to-a-model"></a>方法: モデルにエンティティを追加する
  エンティティを作成するには、Visual Studio の**ツールボックス**から Business Data CONNECTIVITY (BDC) デザイナーにエンティティコントロールを追加します。

### <a name="to-add-an-entity-to-the-model"></a>エンティティをモデルに追加するには

1. BDC プロジェクトを作成するか、既存の BDC プロジェクトを開きます。 詳細については、「[ビジネスデータ接続モデルを作成する](../sharepoint/creating-a-business-data-connectivity-model.md)」を参照してください。

2. **ツールボックス**の**BusinessDataCatalog**グループから、**エンティティ**コントロールをデザイナーに追加します。

     新しいエンティティがデザイナーに表示されます。 Visual Studio により、プロジェクト内の BDC モデルファイルの XML に `<Entity>` 要素が追加されます。 エンティティ要素の属性の詳細については、「 [entity](/previous-versions/office/developer/sharepoint-2010/ee558325(v=office.14))」を参照してください。

3. デザイナーで、エンティティのショートカットメニューを開き、 **[追加]** を選択し、 **[識別子]** を選択します。

     エンティティに新しい識別子が表示されます。

    > [!NOTE]
    > エンティティの名前と識別子は、 **[プロパティ]** ウィンドウで変更できます。

4. クラスのエンティティのフィールドを定義します。 新しいクラスをプロジェクトに追加するか、またはオブジェクトリレーショナルデザイナー (O/R デザイナー) などの他のツールを使用して作成された既存のクラスを使用することができます。 Contact という名前のエンティティクラスの例を次に示します。

     [!code-csharp[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/CSharp/sp_bdc_entity_data_class/bdcmodel1/contact.cs#1)]
     [!code-vb[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/VisualBasic/sp_bdc_entity_data_class/bdcmodel1/contact.vb#1)]

## <a name="see-also"></a>関連項目
- [方法: Creator メソッドを追加する](../sharepoint/how-to-add-a-creator-method.md)
- [方法: 削除子メソッドを追加する](../sharepoint/how-to-add-a-deleter-method.md)
- [方法: Updater メソッドを追加する](../sharepoint/how-to-add-an-updater-method.md)
- [方法: Finder メソッドを追加する](../sharepoint/how-to-add-a-finder-method.md)
- [方法: 特定の Finder メソッドを追加する](../sharepoint/how-to-add-a-specific-finder-method.md)

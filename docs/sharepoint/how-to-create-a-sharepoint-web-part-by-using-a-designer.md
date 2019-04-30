---
title: '方法: デザイナーを使用して SharePoint Web パーツを作成する |Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Web Parts [SharePoint development in Visual Studio], designer
- Web Parts [SharePoint development in Visual Studio], adding
- Web Parts [SharePoint development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 354fe62914a8708ac63acdde7d30060aca8d52fe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62966825"
---
# <a name="how-to-create-a-sharepoint-web-part-by-using-a-designer"></a>方法: デザイナーを使用して、SharePoint Web パーツを作成します。
  Web パーツを作成するには追加することで、**視覚的 Web パーツ**を SharePoint プロジェクト項目。 これを行うと、Visual Studio で Visual Web Developer デザイナーが開きます。このデザイナーでは、コントロールとコードを Web パーツに追加できます。 視覚的 Web パーツは Web パーツと同じように機能します。 唯一の違いは、視覚的 Web パーツのデザインは Visual Web Developer デザイナーで行うことです。

### <a name="to-create-a-project-for-visual-web-parts"></a>視覚的 Web パーツのプロジェクトを作成するには

1. メニュー バーで、**[ファイル]**  > **[新規作成]**  >  **[プロジェクト]** を選択します。

     **[新しいプロジェクト]** ダイアログ ボックスが表示されます。

2. **新しいプロジェクト** ダイアログ ボックスで、いずれかで**Visual c#** または**Visual Basic**、展開、 **Office/sharepoint**ノードを選び、**SharePoint ソリューション**カテゴリ。

3. プロジェクト テンプレートの一覧で選択**SharePoint 2013 - 視覚的 Web パーツ**、選択し、 **OK**ボタンをクリックします。

     **SharePoint カスタマイズ ウィザード**が表示されます。

4. **デバッグのサイトとセキュリティのレベルを指定**] ページで、ローカル コンピューター上にある SharePoint サイトの URL を指定し、[、**完了**ボタンをクリックします。

     **ソリューション エクスプ ローラー**、web パーツが表示されます。 Visual Web Developer デザイナーで、web パーツをデザインした後に、指定したサイトでテストします。

### <a name="to-add-a-visual-web-part-to-an-existing-sharepoint-project"></a>既存の SharePoint プロジェクトに視覚的 Web パーツを追加するには

1. メニュー バーで **[プロジェクト]** > **[新しい項目の追加]** の順に選択します。

2. **新しい項目の追加** ダイアログ ボックスで、選択、 **Office/sharepoint**ノード。

3. プロジェクト テンプレートの一覧で選択**視覚的 Web パーツ**、名前を付け、および選択し、**追加**ボタンをクリックします。

     **ソリューション エクスプ ローラー**、web パーツが表示されます。 Visual Web Developer デザイナーで、web パーツをデザインした後に、指定したサイトでテストします。

## <a name="see-also"></a>関連項目
- [For SharePoint の web パーツを作成します。](../sharepoint/creating-web-parts-for-sharepoint.md)
- [方法: SharePoint web パーツを作成します。](../sharepoint/how-to-create-a-sharepoint-web-part.md)
- [チュートリアル: For SharePoint の web パーツを作成します。](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)
- [チュートリアル: デザイナーを使用して、SharePoint の web パーツを作成します。](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)

---
title: Interop アクティビティ デザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Interop.UI
ms.assetid: 800a3403-ba86-41c4-8de1-c4fee9703eb1
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 55829e85b17bcdc70e419a8496d4756d0acb4a56
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973123"
---
# <a name="interop-activity-designer"></a>Interop アクティビティ デザイナー
**相互運用機能**作成および構成するアクティビティ デザイナーが使用される、<xref:System.Activities.Statements.Interop>アクティビティ。  
  
## <a name="the-interop-activity"></a>Interop アクティビティ  
 <xref:System.Activities.Statements.Interop> アクティビティでは、ワークフロー内の <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName> から派生する型の実行を管理します。  
  
### <a name="using-the-interop-activity-designer"></a>Interop アクティビティ デザイナーの使用  
 **相互運用機能**アクティビティ デザイナーが記載されて、**移行**のカテゴリ、**ツールボックス**をクリックしてアクセスする、**ツールボックス** タブ (または、選択**ツールボックス**から、**ビュー**メニューまたは CTRL + ALT + X)。  
  
 [移行](../workflow-designer/migration-activity-designers.md)格納しているカテゴリ、<xref:System.Activities.Statements.Interop>アクティビティにのみ表示、**ツールボックス**場合は、プロジェクトのターゲットは、完全な[!INCLUDE[netfx40_long](../includes/netfx40-long-md.md)]します。  
  
 C# プロジェクトの場合は、プロジェクトを使用して、完全な再ターゲットできます[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]でプロジェクトを右クリックして、**ソリューション エクスプ ローラー**選択**プロパティ**します。 **アプリケーション**] タブで、[、 **NET Framework 4**オプション、**ターゲット フレームワーク**します。 選択、**はい**ボタン、**ターゲット フレームワークの変更**すると、この変更の確認を求めるために表示されるダイアログ ボックス。  
  
 VB プロジェクトの場合は、プロジェクトを使用して、完全な再ターゲットできます[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]でプロジェクトを右クリックして、**ソリューション エクスプ ローラー**選択**プロパティ**します。 **コンパイル**タブをクリックし、**詳細コンパイル オプション**ボタン。 選択 **.Net Framework 4**から、**ターゲット フレームワーク リスト**順にクリックします**OK**します。 をクリックして、**はい**ボタン、**ターゲット フレームワークの変更**すると、この変更の確認を求めるために表示されるダイアログ ボックス。  
  
 **相互運用機能**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**ドロップ、[!INCLUDE[wfd2](../includes/wfd2-md.md)]サーフェス任意の場所、アクティビティを通常配置など内、<xref:System.Activities.Statements.Sequence>します。 これを作成、 <xref:System.Activities.Statements.Interop> 、既定値は、アクティビティ**DisplayName**の相互運用機能。 <xref:System.Activities.Activity.DisplayName%2A>のヘッダーで編集できる、**相互運用機能**アクティビティ デザイナーまたは、 **DisplayName**プロパティ グリッドのボックスです。  
  
 をクリックして、 **[参照] をクリックします.** 内のテキスト、 **ActivityType**ボックス、**相互運用機能**アクティビティ デザイナーまたはプロパティ グリッドを表示、**型の参照と選択を .Net**  ダイアログ ボックス。 ワークフロー 3.0 またはワークフロー 3.5 のアクティビティの型のみ (つまり、<xref:System.Workflow.ComponentModel.Activity> から派生した型のみ) が表示されます。 [!INCLUDE[crabout](../includes/crabout-md.md)] 参照型を指定するには、このボックスを使用して、[参照し、.NET の種類 ダイアログ ボックスを選択](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box.md)トピック。  
  
### <a name="the-interop-properties"></a>Interop のプロパティ  
 次の表に、<xref:System.Activities.Statements.Interop> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドまたは[!INCLUDE[wfd2](../includes/wfd2-md.md)]画面で編集できます。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Interop> アクティビティの表示名。 既定値は Interop です。 表示名は必須ではありませんが、使用することをお勧めします。|  
|<xref:System.Activities.Statements.Interop.ActivityType%2A>|True|<xref:System.Activities.Statements.Interop> アクティビティに含まれているアクティビティの型を指定します。 指定されたこの型は、<xref:System.Workflow.ComponentModel.Activity> から派生していることが必要です。|  
  
## <a name="see-also"></a>関連項目  
 [移行](../workflow-designer/migration-activity-designers.md)
---
title: Throw アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
caps.latest.revision: 4
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1855daa5016241fb6eb04f05d7218e02083fc0a8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72655158"
---
# <a name="throw-activity-designer"></a>Throw アクティビティ デザイナー
**Throw**アクティビティデザイナーは、<xref:System.Activities.Statements.Throw> アクティビティを作成および構成するために使用されます。

## <a name="the-throw-activity"></a>Throw アクティビティ
 <xref:System.Activities.Statements.Throw> アクティビティによって例外がスローされます。

### <a name="using-the-throw-activity-designer"></a>Throw アクティビティ デザイナーの使用
 **Throw**アクティビティデザイナーは、 **[ツールボックス]** の **[エラー処理]** カテゴリにあります。これにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)] の左側にある **[ツールボックス]** タブをクリックします (または、ビューから **[ツールバー]** を選択します)。メニューまたは CTRL + ALT + X)

 **Throw**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) にドロップして [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 これにより、Throw という既定の**DisplayName**を持つ <xref:System.Activities.Statements.Throw> アクティビティが作成されます。 @No__t_0 値は、 **Throw**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。 この <xref:System.Activities.Statements.Throw.Exception%2A> プロパティは、プロパティ グリッドで編集する必要があります。

### <a name="the-throw-properties"></a>Throw プロパティ
 次の表に、<xref:System.Activities.Statements.Throw> のプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Throw> アクティビティの表示名を指定します (省略可能)。 既定値は Throw です。|
|<xref:System.Activities.Statements.Throw.Exception%2A>|True|スローされる例外。 この例外は、<xref:System.Exception> から派生していることが必要です。 例外を指定するには、プロパティ グリッドで Visual Basic の式を入力します。|

## <a name="see-also"></a>参照
 [コレクション](../workflow-designer/collection-activity-designers.md)[再スロー](../workflow-designer/rethrow-activity-designer.md) [スローアクティビティデザイナー](../workflow-designer/throw-activity-designer.md) [TryCatch](../workflow-designer/trycatch-activity-designer.md)
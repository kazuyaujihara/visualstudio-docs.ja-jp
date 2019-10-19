---
title: ワークフローデザイナー TerminateWorkflow アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 01003005e9f73138e5a430b21e538c5c241e7f9f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649883"
---
# <a name="terminateworkflow-activity-designer"></a>TerminateWorkflow アクティビティ デザイナー

**TerminateWorkflow**アクティビティデザイナーは、<xref:System.Activities.Statements.TerminateWorkflow> アクティビティを作成および構成するために使用されます。

## <a name="the-terminateworkflow-activity"></a>TerminateWorkflow アクティビティ

<xref:System.Activities.Statements.TerminateWorkflow> アクティビティは、ワークフローの実行を停止します。

### <a name="using-the-terminateworkflow-activity-designer"></a>TerminateWorkflow アクティビティ デザイナーの使用

**TerminateWorkflow**アクティビティデザイナーは、 **[ツールボックス**] の **[ランタイム]** カテゴリにあります。このカテゴリにアクセスするには、 **[ツール]** ボックス タブをクリックします (または、 **[表示]** メニューの **[ツールボックス]** を選択するか、CTRL + ALT + キーを押します。X)

**TerminateWorkflow**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) にドロップしてワークフローデザイナー画面にドロップできます。 これにより、TerminateWorkflow という既定の**DisplayName**を持つ <xref:System.Activities.Statements.TerminateWorkflow> アクティビティが作成されます。 @No__t_0 は、 **TerminateWorkflow**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

### <a name="the-terminateworkflow-properties"></a>TerminateWorkflow のプロパティ

次の表に、<xref:System.Activities.Statements.TerminateWorkflow> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティグリッドで編集することができ、一部のプロパティはワークフローデザイナー画面で編集できます。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TerminateWorkflow> アクティビティの表示名。 既定値は TerminateWorkflow です。 表示名は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|ワークフローが停止されたときにスローする例外。 このプロパティは、プロパティ グリッドで設定します。|
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|ワークフローが停止された理由。 このプロパティは、プロパティ グリッドで設定します。|

## <a name="see-also"></a>関連項目

- [ランタイム](../workflow-designer/runtime-activity-designers.md)
- [Persist](../workflow-designer/persist-activity-designer.md)
---
title: 場合アクティビティ デザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3ab8c9a7f49302b2308f97855c022d8e8d5126e0
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976805"
---
# <a name="if-activity-designer"></a>If アクティビティ デザイナー
<xref:System.Activities.Statements.If> アクティビティでは、条件を評価し、その評価の結果に応じてアクティビティを実行します。 このアクティビティは、手順型モデルのプログラミング スタイルを使用する場合に最も役立ちます。 <xref:System.Activities.Statements.If> アクティビティは、<xref:System.Activities.Statements.Sequence> アクティビティや <xref:System.Activities.Statements.Parallel> アクティビティなどの内部に入れ子にすることができます。 <xref:System.Activities.Statements.Flowchart> アクティビティを使用している場合は、代わりに、<xref:System.Activities.Statements.FlowDecision> アクティビティの使用を検討してください。  
  
## <a name="if-properties-in-the-workflow-designer"></a>ワークフロー デザイナーでの If のプロパティ  
 次の表に、最も役に立つ <xref:System.Activities.Statements.If> アクティビティのプロパティと、デザイナーでのその使用方法を示します。  
  
|プロパティ名|必須|使用法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.If.Condition%2A>|True|実行する子アクティビティを決定する条件。 設定する、 <xref:System.Activities.Statements.If.Condition%2A>、タイプ a[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]内の式、**条件**ボックスに、**場合**アクティビティ デザイナーまたはプロパティ グリッドで。|  
|<xref:System.Activities.Statements.If.Else%2A>|False|場合に実行されるアクティビティ、<xref:System.Activities.Statements.If.Condition%2A>は**false**します。 によって実行されるアクティビティを追加する、<xref:System.Activities.Statements.If.Else%2A>分岐からアクティビティ、**ツールボックス**に、 **Else**ボックスに、**場合**アクティビティ デザイナーのヒント テキスト"ここにアクティビティをドロップ"。|  
|<xref:System.Activities.Statements.If.Then%2A>|False|場合に実行されるアクティビティ、<xref:System.Activities.Statements.If.Condition%2A>は**true**します。 によって実行されるアクティビティを追加する、<xref:System.Activities.Statements.If.Then%2A>分岐からアクティビティ、**ツールボックス**に、**し**ボックスに、**場合**アクティビティ デザイナーのヒント テキスト"ここにアクティビティをドロップ"。|  
  
## <a name="see-also"></a>関連項目  
 [シーケンス](../workflow-designer/sequence-activity-designer.md)   
 [並列](../workflow-designer/parallel-activity-designer.md)   
 [制御フロー](../workflow-designer/control-flow-activity-designers.md)
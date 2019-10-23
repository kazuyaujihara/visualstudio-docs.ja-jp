---
title: FinalState アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: aa186893-8775-40dd-981f-8593ead831d0
caps.latest.revision: 5
author: steved0x
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dff9793becc3e0619d42b642609273f328c6aa73
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656721"
---
# <a name="finalstate-activity-designer"></a>FinalState アクティビティ デザイナー
<xref:System.Activities.Core.Presentation.FinalState> デザイナーは、ステート マシンのインスタンスを終了する <xref:System.Activities.Statements.State> を作成するために使用されます。

## <a name="using-the-finalstate-activity-designer"></a>FinalState アクティビティ デザイナーの使用
 **Finalstate**デザイナーは、ステートマシンで終了状態として事前に構成されている <xref:System.Activities.Statements.State> を作成するために使用されます。 @No__t_1 アクティビティデザイナーを使用して作成された <xref:System.Activities.Statements.State> では、<xref:System.Activities.Statements.State.IsFinal%2A> プロパティが**true**に設定されており、<xref:System.Activities.Statements.State.Exit%2A> アクティビティがなく、そこからの遷移はありません。 @No__t_0 アクティビティデザイナーを使用して、ステートマシンで終了状態として事前に構成されている <xref:System.Activities.Statements.State> アクティビティを追加するには、 **[ツールボックス]** の **[ステートマシン]** セクションから**finalstate**アクティビティデザイナーをドラッグし、ワークフローデザイナー。 <xref:System.Activities.Core.Presentation.FinalState> アクティビティ デザイナーは、<xref:System.Activities.Statements.StateMachine> にドロップして遷移を後で追加できます。または遷移は、<xref:System.Activities.Core.Presentation.FinalState> アクティビティ デザイナーをドロップしたときに作成できます。 遷移の作成の詳細については、「 [Transition](../workflow-designer/transition-activity-designer.md)」を参照してください。

### <a name="state-activity-properties-in-the-workflow-designer"></a>ワークフロー デザイナーでの State アクティビティのプロパティ
 次の表に、<xref:System.Activities.Core.Presentation.FinalState> デザイナーを使用して設定できるプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティの中には、プロパティ グリッドで編集できるものがあります。また、その一部はデザイナー画面で編集できます。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|ヘッダーの <xref:System.Activities.Statements.State> アクティビティ デザイナーの表示名を指定します。 既定値は**State**です。 この値は、プロパティ グリッドで編集することも、アクティビティ デザイナーのヘッダーで直接編集することもできます。 <xref:System.Activities.Statements.State.DisplayName%2A> は、ワークフロー デザイナーの上部に表示される階層リンク バーで使用されます。<br /><br /> <xref:System.Activities.Statements.State.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.State.Entry%2A>|False|この状態の遷移時に発生するアクションを指定します。 この値を設定するには、**ツールボックス**からアクティビティをドラッグし、状態の <xref:System.Activities.Statements.State.Entry%2A> セクションにドロップします。|

## <a name="see-also"></a>参照
 [StateMachine](../workflow-designer/statemachine-activity-designer.md) [状態](../workflow-designer/state-activity-designer.md)[遷移](../workflow-designer/transition-activity-designer.md)
---
title: ワークフローデザイナー TransactedReceiveScope アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cf5a52a6a806d72632bf31a7c73e41677e9ddaf9
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654290"
---
# <a name="transactedreceivescope-activity-designer"></a>TransactedReceiveScope アクティビティ デザイナー

**TransactedReceiveScope**デザイナーは、<xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティを作成および構成するために使用されます。

## <a name="the-transactedreceivescope-activity"></a>TransactedReceiveScope アクティビティ

<xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティを使用すると、ワークフローまたはディスパッチャーによって作成されたサーバー トランザクションにトランザクションをフローできます。

### <a name="using-the-transactedreceivescope-activity-designer"></a>TransactedReceiveScope アクティビティ デザイナーの使用

**ツールボックス**の **[メッセージング]** カテゴリの**TransactedReceiveScope**アクティビティデザイナーにアクセスします。 **TransactedReceiveScope**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所のワークフローデザイナー画面にドロップできます。 これにより、TransactedReceiveScope という既定の**DisplayName**を持つ <xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティが作成されます。 @No__t_0 は、 **TransactedReceiveScope**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

**TransactedReceiveScope**デザイナーには、 **[要求]** ボックスと **[本文]** ボックスがあります。 これらは、<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> プロパティを構成するために使用します。このプロパティでは、<xref:System.ServiceModel.Activities.Receive> アクティビティと、他の <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> を指定する <xref:System.Activities.Activity> プロパティを指定します。 <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> によって、トランザクションが作成されます。 その後、トランザクションはこのスコープのアンビエント トランザクションになり、<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> のスコープ内のあらゆるアクティビティは、このトランザクション内で実行されます。

### <a name="the-transactedreceivescope-properties"></a>TransactedReceiveScope のプロパティ

次の表に、<xref:System.ServiceModel.Activities.TransactedReceiveScope> のプロパティと、デザイナーでのその使用方法を示します。 これらの <xref:System.Activities.Activity.DisplayName%2A> プロパティは、プロパティグリッドまたはワークフローデザイナー画面で編集できますが、他のプロパティはデザインサーフェイスで編集する必要があります。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティの省略可能な表示名。 既定値は、TransactedReceiveScope です。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> 名は必須ではありませんが、使用することをお勧めします。|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|True|アクティビティデザイナー画面の**要求**ブロックに <xref:System.ServiceModel.Activities.Receive> アクティビティをドロップします。|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|False|アクティビティデザイナー画面の**本文**ブロックに <xref:System.Activities.Activity> をドロップします。|

## <a name="see-also"></a>関連項目

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Receive](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Send](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
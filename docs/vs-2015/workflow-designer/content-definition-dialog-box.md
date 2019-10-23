---
title: '[コンテンツ定義] ダイアログボックス |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
caps.latest.revision: 3
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d989f5a0c57e381041e8fe9c200aae1a76316ad8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656960"
---
# <a name="content-definition-dialog-box"></a>[コンテンツ定義] ダイアログ ボックス
**[コンテンツ定義]** ダイアログボックスは、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.SendReply>、および <xref:System.ServiceModel.Activities.ReceiveReply> の各アクティビティの**コンテンツ**プロパティを構成するために [!INCLUDE[wfd1](../includes/wfd1-md.md)] で使用されます。 このボックスを使用するアクティビティデザイナーを [!INCLUDE[crabout](../includes/crabout-md.md)] には、「 [Send](../workflow-designer/send-activity-designer.md)、 [Receive](../workflow-designer/receive-activity-designer.md)、 [Receiveandsendreply](../workflow-designer/receiveandsendreply-template-designer.md)、および[sendandreceivereply](../workflow-designer/sendandreceivereply-template-designer.md) 」のトピックを参照してください。

 次の表では、 **[関連付けの初期化]** ダイアログボックスのユーザーインターフェイス (UI) 要素について説明します。

|UI 要素|説明|
|----------------|-----------------|
|**[メッセージ]**|メッセージの **[データ]** 式 テキストボックスと、 **[メッセージの種類]** ドロップダウンリストボックスを使用して、メッセージの内容を指定します。 既定では、**コンテンツ定義**は、ワークフローサービス定義内で <xref:System.ServiceModel.Channels.Message> またはメッセージコントラクト型を必要とする <xref:System.ServiceModel.Activities.ReceiveMessageContent> を使用します。|
|**パラメーター**|**[パラメーター]** オプションボタンをクリックして <xref:System.ServiceModel.Activities.ReceiveParametersContent> を使用します。これにはデータコントラクトが必要です。 <xref:System.Activities.OutArgument> キーおよび値のペアのジェネリック コレクションを設定するには、データ グリッドを使用します。これらの値は、現在のワークフローの変数パラメーターに割り当てられます。|

 **[コンテンツ定義]** ダイアログボックスは、 **Send**、 **Receive**、 **Receiveandsendreply**、および**sendandreceivereply**の各デザイナーによって使用されます。 デザイナーへのアクセス方法は、どの場合も同様です。ここでは、Receive デザイナーを使用する例で手順を説明します。

 **Receive**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所の [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 この操作により、Receive という既定の <xref:System.ServiceModel.Activities.Receive> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 **Receive**アクティビティデザイナーを選択し、[コンテンツ**定義**] ダイアログボックスが表示されるプロパティグリッドで、**コンテンツ**プロパティの (コンテンツ) テキストの横にある省略記号ボタンをクリックします。

 コンテンツは、<xref:System.ServiceModel.Activities.ReceiveMessageContent> アクティビティの場合は**Message**セクション内で指定することも、<xref:System.ServiceModel.Activities.ReceiveParametersContent> アクティビティの場合は**Parameter**セクション内で指定することもできます。

## <a name="see-also"></a>参照
 [ワークフロー デザイナーの UI ヘルプ](../workflow-designer/workflow-designer-ui-help.md)
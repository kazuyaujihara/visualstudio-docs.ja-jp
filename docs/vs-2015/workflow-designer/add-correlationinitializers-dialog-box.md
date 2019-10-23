---
title: '[CorrelationInitializers の追加] ダイアログボックス |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- AddCorrelationInitializers.UI
ms.assetid: c0517467-d54a-4ee6-aef0-c19b96b6f395
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e1402b90dfc78068546b510ce6b85379b1695f47
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672037"
---
# <a name="add-correlationinitializers-dialog-box"></a>[関連付け初期化子の追加] ダイアログ ボックス
@No__t_1 では、 **[関連付け初期化子の追加]** ダイアログボックスを使用して、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.SendReply>、および <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティの**correlationinitializers**プロパティを構成します。 このボックスを使用するアクティビティデザイナーを [!INCLUDE[crabout](../includes/crabout-md.md)] には、「 [Send](../workflow-designer/send-activity-designer.md)、 [Receive](../workflow-designer/receive-activity-designer.md)、 [Receiveandsendreply](../workflow-designer/receiveandsendreply-template-designer.md)、および[sendandreceivereply](../workflow-designer/sendandreceivereply-template-designer.md) 」のトピックを参照してください。

 このダイアログ ボックスで指定したコレクションの関連付け初期化子では、メッセージング アクティビティ間の相関関係 (クエリベース、コンテキスト、コールバック コンテキスト、または要求/応答の相関関係) を初期化できます。

 次の表では、 **[関連付け初期化子の追加]** ダイアログボックスのユーザーインターフェイス (UI) 要素について説明します。

|UI 要素|説明|
|----------------|-----------------|
|**初期化子の追加**|**[初期化の追加]** ボックスをクリックして、追加の初期化子をコレクションに追加します。|
|**関連付けの種類**|関連付け初期化子の種類を指定します。 次の 4 種類から選択できます。<br /><br /> 1. <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer> を指定するコールバック関連付け初期化子。<br />2. <xref:System.ServiceModel.Activities.CorrelationInitializer> を指定するコンテキスト関連付け初期化子。<br />3. <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> を指定するための要求と応答の関連付け初期化子。<br />4. <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> を指定するためのクエリ関連付け初期化子。<br /><br /> **Correlationtype**を編集するには<br /><br /> 1. **[初期化子の追加]** DataGrid の特定の行にタブを追加します。<br />2. Ctrl + Tab キーを押して、 **Correlationtypecombobox**にフォーカスを設定します<br />3. Alt + ↓キーを押して、**コンボボックス**をポップアップ表示して編集します。|
|**XPath クエリ**|送受信メッセージから相関関係データを抽出するためのクエリを含む、キーと値のペア。 このリストは、<xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 型を使用している場合にのみ有効です。|

## <a name="to-launch-the-add-correlation-initializers-dialog-box"></a>[関連付け初期化子の追加] ダイアログ ボックスを開くには
 **[関連付け初期化子の追加]** ダイアログボックスは、 **Send**、 **Receive**、 **Receiveandsendreply**、および**sendandreceivereply**の各デザイナーによって使用されます。 これらのアクセスは、各ケースで類似しています。また、**受信**デザイナーに関連するケースでは、この手順を説明するために使用します。

 **Receive**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所の [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 この操作により、Receive という既定の <xref:System.ServiceModel.Activities.Receive> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 **Receive**アクティビティデザイナーを選択し、 **[関連付け初期化子の追加]** ダイアログボックスのプロパティグリッドで、 **Correlationinitializers**プロパティの (コレクション) テキストの横にある省略記号ボタンをクリックします。

## <a name="see-also"></a>参照
 [[関連付け初期化] ダイアログ ボックス](../workflow-designer/initialize-correlation-dialog-box.md)
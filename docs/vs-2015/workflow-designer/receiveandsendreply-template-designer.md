---
title: ReceiveAndSendReply テンプレートデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.ReceiveAndSendReply.UI
- System.ServiceModel.Activities.SendReply.UI
ms.assetid: d1d9a058-df7e-48f5-a2e7-3caeeba7eaa6
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e853967f73c99aa52958754e9f59f644c2f9497b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672542"
---
# <a name="receiveandsendreply-template-designer"></a>ReceiveAndSendReply テンプレート デザイナー
**Receiveandsendreply**テンプレートを使用して、サーバー上で要求/応答メッセージ交換パターンの一部として関連付けられている <xref:System.Activities.Statements.Sequence> アクティビティ内に、事前に構成された <xref:System.ServiceModel.Activities.Receive> と <xref:System.ServiceModel.Activities.SendReply> アクティビティのペアを作成します。

## <a name="the-receiveandsendreply-template"></a>ReceiveAndSendReply テンプレート
 **Receiveandsendreply**テンプレートの追加には、<xref:System.ServiceModel.Activities.Receive> の作成と、<xref:System.Activities.Statements.Sequence> アクティビティを使用したアクティビティの <xref:System.ServiceModel.Activities.SendReply> の3つの操作が含まれます。

1. <xref:System.ServiceModel.Activities.Receive.OperationName%2A> アクティビティの <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> プロパティと <xref:System.ServiceModel.Activities.Receive> プロパティを構成する。

2. <xref:System.ServiceModel.Activities.SendReply.Request%2A> アクティビティの <xref:System.ServiceModel.Activities.Receive> プロパティを <xref:System.ServiceModel.Activities.Send> アクティビティにバインドする。

3. 親アクティビティに、変数として <xref:System.ServiceModel.Activities.CorrelationHandle> を作成する。

### <a name="using-the-receiveandsendreply-template-designer"></a>ReceiveAndSendReply テンプレート デザイナーの使用
 **Receiveandsendreply**アクティビティデザイナーは、ツール **[ボックス]** の **[メッセージング]** カテゴリにあります。これにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)] の **[ツールボックス]** タブをクリックします (または、**ビュー**から **[ツールバー]** を選択します)。メニューまたは CTRL + ALT + X)

 **Receiveandsendreply**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所で [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 これにより、 **Send**アクティビティデザイナーで構成できる <xref:System.ServiceModel.Activities.Receive> アクティビティと、SendReplyToReceive デザイナーで構成できる関連 <xref:System.ServiceModel.Activities.SendReply> が作成されます。

 **receive** designer を使用して <xref:System.ServiceModel.Activities.Receive> アクティビティを構成 [!INCLUDE[crabout](../includes/crabout-md.md)] につい[ては、「」を](../workflow-designer/receive-activity-designer.md)参照してください。

 **SendReplyToReceive**デザイナーを使用して <xref:System.ServiceModel.Activities.SendReply> アクティビティを構成する [!INCLUDE[crabout](../includes/crabout-md.md)]、次のセクションを参照してください。

### <a name="properties-of-sendreply"></a>SendReply のプロパティ
 次の表に、<xref:System.ServiceModel.Activities.SendReply> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドで編集できます。また、その一部は[!INCLUDE[wfd2](../includes/wfd2-md.md)]のデザイナー画面で編集できます。

|                               プロパティ名                                | 必要 |                                                                                                                                                                                                                                                                                                                                                      使用方法                                                                                                                                                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              <xref:System.Activities.Activity.DisplayName%2A>              |  False   |                                                                                                                                                                                            <xref:System.ServiceModel.Activities.SendReply> アクティビティの省略可能な表示名。 既定値は SendReplyToReceive です。<br /><br /> 既定値以外の <xref:System.Activities.Activity.DisplayName%2A> の使用は必須ではありませんが、使用することをお勧めします。                                                                                                                                                                                             |
|         <xref:System.ServiceModel.Activities.SendReply.Request%2A>         |   True   | この <xref:System.ServiceModel.Activities.Receive> アクティビティと関連付けられる <xref:System.ServiceModel.Activities.SendReply> アクティビティへの参照。 このプロパティを**null**にすることはできません。 <xref:System.ServiceModel.Activities.Receive> アクティビティと <xref:System.ServiceModel.Activities.SendReply> アクティビティは、要求/応答メッセージ パターンをモデル化するためにサーバーで一緒に使用されます。 このプロパティでは、関連付ける <xref:System.ServiceModel.Activities.Send> アクティビティを指定します。 このプロパティは、<xref:System.ServiceModel.Activities.Send> アクティビティの作成元である <xref:System.ServiceModel.Activities.SendReply> アクティビティに自動的にバインドされるため、デザイナーでは編集できません。 |
|         <xref:System.ServiceModel.Activities.SendReply.Content%2A>         |  False   |                       受信するメッセージまたはパラメーターの内容を指定します。 <xref:System.ServiceModel.Activities.ReceiveMessageContent> アクティビティまたは <xref:System.ServiceModel.Activities.ReceiveParametersContent> アクティビティを指定できます。 このプロパティを編集するには、プロパティグリッドで**コンテンツ**フィールドの横にある省略記号ボタンをクリックするか、 **[定義...]** をクリックします。 **Receive**アクティビティデザイナー画面の**コンテンツ**ラベルの横にあるボタン。 どちらの場合も、 **[コンテンツ定義]** ダイアログボックスが表示されます。 このボックスの使用方法 [!INCLUDE[crabout](../includes/crabout-md.md)] ては、「[コンテンツ定義」ダイアログボックス](../workflow-designer/content-definition-dialog-box.md)のトピックを参照してください。                       |
| <xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A> |  False   |            ワークフロー内のこの <xref:System.ServiceModel.Activities.CorrelationInitializer> アクティビティを構成する複数の <xref:System.ServiceModel.Activities.CorrelationHandle> オブジェクトを初期化する <xref:System.ServiceModel.Activities.Receive> オブジェクトのコレクションを指定します。 プロパティグリッドの [<xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A>] プロパティの横にある省略記号ボタンをクリックして、 **[関連付け初期化子の追加]** ダイアログボックスを開きます。 このボックスを使用 [!INCLUDE[crabout](../includes/crabout-md.md)] には、[ [CorrelationInitializers の追加] ダイアログボックス](../workflow-designer/add-correlationinitializers-dialog-box.md)のトピックを参照してください。            |
|         <xref:System.ServiceModel.Activities.SendReply.Action%2A>          |  False   |                                                                                                                                                                                                                                              メッセージのアクション ヘッダーを指定します。 これを明示的に設定しない場合は、次の既定値が設定されます。<br /><br /> <strong>https://tempuri.org/{service コントラクト名前空間}/{サービスコントラクト名}/{操作名}</strong>                                                                                                                                                                                                                                              |
|    <xref:System.ServiceModel.Activities.SendReply.PersistBeforeSend%2A>    |  False   |                                                                                                                                                                                                                                                                                          応答メッセージを送信する前にワークフロー サービス インスタンスを永続化するかどうかを指定します。 既定値は **false** です。                                                                                                                                                                                                                                                                                           |

## <a name="see-also"></a>参照
 [Correlationscope](../workflow-designer/correlationscope-activity-designer.md) [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md) [Receive](../workflow-designer/receive-activity-designer.md) [Send](../workflow-designer/send-activity-designer.md) [sendandreceivereply](../workflow-designer/sendandreceivereply-template-designer.md) [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)
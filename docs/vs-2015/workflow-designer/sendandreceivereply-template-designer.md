---
title: SendAndReceiveReply テンプレートデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.SendAndReceiveReply.UI
- System.ServiceModel.Activities.ReceiveReply.UI
ms.assetid: 818a8c84-6593-416d-b016-1d91b85ffb68
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 4ecb0e201c4351a8a117d1e35aca97866b2beb89
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663269"
---
# <a name="sendandreceivereply-template-designer"></a>SendAndReceiveReply テンプレート デザイナー
**Sendandreceivereply**テンプレートを使用して、クライアントでの要求/応答メッセージ交換パターンの一部として関連付けられている <xref:System.Activities.Statements.Sequence> アクティビティ内に、事前に構成された <xref:System.ServiceModel.Activities.Send> と <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティのペアを作成します。

## <a name="the-sendandreceivereply-template"></a>SendAndReceiveReply テンプレート
 **Sendandreceivereply**テンプレートを追加するには、<xref:System.Activities.Statements.Sequence> アクティビティ内で <xref:System.ServiceModel.Activities.Send> と <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティを作成する以外に、次の3つの操作を行います。

1. <xref:System.ServiceModel.Activities.Send.OperationName%2A> アクティビティの <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> プロパティと <xref:System.ServiceModel.Activities.Send> プロパティを構成する。

2. <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> アクティビティの <xref:System.ServiceModel.Activities.ReceiveReply> プロパティを <xref:System.ServiceModel.Activities.Send> アクティビティにバインドする。

3. 親アクティビティに、変数として <xref:System.ServiceModel.Activities.CorrelationHandle> を作成する。

### <a name="using-the-sendandreceivereply-template-designer"></a>SendAndReceiveReply テンプレート デザイナーの使用
 **Sendandreceivereply**アクティビティデザイナーは、ツール **[ボックス]** の **[メッセージング]** カテゴリにあります。これにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)] の **[ツールボックス]** タブをクリックします (または、**ビュー**から **[ツールバー]** を選択します)。メニューまたは CTRL + ALT + X)

 **Sendandreceivereply**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所で [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 これにより、 **send**アクティビティデザイナーと、 **Receivereplyforsend**デザイナーで構成できる関連 <xref:System.ServiceModel.Activities.ReceiveReply> を使用して構成できる <xref:System.ServiceModel.Activities.Send> アクティビティが作成されます。

 **送信**デザイナーを使用して <xref:System.ServiceModel.Activities.Send> アクティビティを構成 [!INCLUDE[crabout](../includes/crabout-md.md)] には、「[送信](../workflow-designer/send-activity-designer.md)」トピックを参照してください。

 **Receivereplyforsend**デザイナーを使用して <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティを構成 [!INCLUDE[crabout](../includes/crabout-md.md)] には、次のセクションを参照してください。

### <a name="properties-of-receivereply"></a>ReceiveReply のプロパティ
 次の表に、<xref:System.ServiceModel.Activities.ReceiveReply> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドで編集できます。また、その一部は[!INCLUDE[wfd2](../includes/wfd2-md.md)]のデザイナー画面で編集できます。

|                                 プロパティ名                                 | 必要 |                                                                                                                                                                                                                                                                                                                                                        使用方法                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------------------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|               <xref:System.Activities.Activity.DisplayName%2A>                |  False   |                                                                                                                                                                                            <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティの省略可能な表示名。 既定値は、ReceiveReplyForSend です。<br /><br /> 既定値以外の <xref:System.Activities.Activity.DisplayName%2A> の使用は必須ではありませんが、使用することをお勧めします。                                                                                                                                                                                            |
|         <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>         |   True   | この <xref:System.ServiceModel.Activities.Send> アクティビティと関連付けられる <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティへの参照。 このプロパティを**null**にすることはできません。 <xref:System.ServiceModel.Activities.Send> アクティビティと <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティは、要求/応答メッセージ パターンをモデル化するためにクライアントで一緒に使用されます。 このプロパティでは、関連付ける <xref:System.ServiceModel.Activities.Send> アクティビティを指定します。 このプロパティは、<xref:System.ServiceModel.Activities.Send> アクティビティの作成元である <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティに自動的にバインドされるため、デザイナーでは編集できません。 |
|         <xref:System.ServiceModel.Activities.ReceiveReply.Content%2A>         |  False   |                        受信するメッセージまたはパラメーターの内容を指定します。 <xref:System.ServiceModel.Activities.ReceiveMessageContent> アクティビティまたは <xref:System.ServiceModel.Activities.ReceiveParametersContent> アクティビティを指定できます。 このプロパティを編集するには、プロパティグリッドで**コンテンツ**フィールドの横にある省略記号ボタンをクリックするか、 **[定義...]** をクリックします。 **Receive**アクティビティデザイナー画面の**コンテンツ**ラベルの横にあるボタン。 どちらの場合も、 **[コンテンツ定義]** ダイアログボックスが表示されます。 このボックスの使用方法 [!INCLUDE[crabout](../includes/crabout-md.md)] ては、「[コンテンツ定義」ダイアログボックス](../workflow-designer/content-definition-dialog-box.md)のトピックを参照してください。                         |
| <xref:System.ServiceModel.Activities.ReceiveReply.CorrelationInitializers%2A> |  False   |              ワークフロー内のこの <xref:System.ServiceModel.Activities.CorrelationInitializer> アクティビティを構成する複数の <xref:System.ServiceModel.Activities.CorrelationHandle> オブジェクトを初期化する <xref:System.ServiceModel.Activities.Receive> オブジェクトのコレクションを指定します。 プロパティグリッドの [<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>] プロパティの横にある省略記号ボタンをクリックして、 **[関連付け初期化子の追加]** ダイアログボックスを開きます。 このボックスを使用 [!INCLUDE[crabout](../includes/crabout-md.md)] には、[ [CorrelationInitializers の追加] ダイアログボックス](../workflow-designer/add-correlationinitializers-dialog-box.md)のトピックを参照してください。               |
|         <xref:System.ServiceModel.Activities.ReceiveReply.Action%2A>          |  False   |                                                                                                                                                                                                                                               メッセージのアクション ヘッダーを指定します。 これを明示的に設定しない場合は、次の既定値が設定されます。<br /><br /> <strong>https://tempuri.org/{service コントラクト名前空間}/{サービスコントラクト名}/{操作名}。</strong>                                                                                                                                                                                                                                               |

## <a name="see-also"></a>参照
 [Correlationscope](../workflow-designer/correlationscope-activity-designer.md) [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md) [Receive](../workflow-designer/receive-activity-designer.md) [receiveandsendreply](../workflow-designer/receiveandsendreply-template-designer.md) [Send](../workflow-designer/send-activity-designer.md) [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)
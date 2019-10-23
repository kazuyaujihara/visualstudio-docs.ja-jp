---
title: ワークフローデザイナー ReceiveAndSendReply テンプレートデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.ReceiveAndSendReply.UI
- System.ServiceModel.Activities.SendReply.UI
ms.assetid: d1d9a058-df7e-48f5-a2e7-3caeeba7eaa6
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a816013f4eceb390a16e76a06814043aa0adaeb8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650022"
---
# <a name="receiveandsendreply-template-designer"></a>ReceiveAndSendReply テンプレート デザイナー

**Receiveandsendreply**テンプレートを使用して、構成済みの <xref:System.ServiceModel.Activities.Receive> と <xref:System.ServiceModel.Activities.SendReply> アクティビティのペアを作成します。 アクティビティは <xref:System.Activities.Statements.Sequence> アクティビティの一部であり、サーバー上で要求/応答メッセージ交換パターンの一部として関連付けられています。

## <a name="the-receiveandsendreply-template"></a>ReceiveAndSendReply テンプレート

**Receiveandsendreply**テンプレートを追加するには、<xref:System.ServiceModel.Activities.Receive> と <xref:System.ServiceModel.Activities.SendReply> アクティビティを <xref:System.Activities.Statements.Sequence> アクティビティと共に作成する以外に、次の3つの操作を行います。

- @No__t_2 アクティビティの <xref:System.ServiceModel.Activities.Receive.OperationName%2A> および <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> プロパティを構成します。

- <xref:System.ServiceModel.Activities.SendReply.Request%2A> アクティビティの <xref:System.ServiceModel.Activities.Receive> プロパティを <xref:System.ServiceModel.Activities.Send> アクティビティにバインドする。

- 親アクティビティに、変数として <xref:System.ServiceModel.Activities.CorrelationHandle> を作成する。

### <a name="use-the-receiveandsendreply-template-designer"></a>ReceiveAndSendReply テンプレートデザイナーを使用する

**[ツールボックス]** の **[メッセージング]** カテゴリで、 **receiveandsendreply**アクティビティデザイナーにアクセスします。 **Receiveandsendreply**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所でワークフローデザイナー画面にドロップできます。 アクティビティデザイナーを削除すると <xref:System.ServiceModel.Activities.Receive> アクティビティが作成されます。このアクティビティは、 **Send**アクティビティデザイナーと、SendReplyToReceive デザイナーで構成できる関連 <xref:System.ServiceModel.Activities.SendReply> で構成できます。

**Receive** designer を使用して <xref:System.ServiceModel.Activities.Receive> アクティビティを構成する方法の詳細については、「 [receive アクティビティデザイナー](../workflow-designer/receive-activity-designer.md)」を参照してください。

### <a name="properties-of-sendreply"></a>SendReply のプロパティ

次の表に、<xref:System.ServiceModel.Activities.SendReply> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、[プロパティ] グリッドで編集できます。また、一部のプロパティは、ワークフローデザイナー画面で編集できます。

| プロパティ名 | 必要 | 使用方法 |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | False | <xref:System.ServiceModel.Activities.SendReply> アクティビティの省略可能な表示名。 既定値は SendReplyToReceive です。<br /><br /> フレンドリ <xref:System.Activities.Activity.DisplayName%2A> に既定値以外の値を使用することは、厳密には必須ではありませんが、このような値を使用することをお勧めします。 |
| <xref:System.ServiceModel.Activities.SendReply.Request%2A> | True | この <xref:System.ServiceModel.Activities.Receive> アクティビティと関連付けられる <xref:System.ServiceModel.Activities.SendReply> アクティビティへの参照。 このプロパティを**null**にすることはできません。 <xref:System.ServiceModel.Activities.Receive> アクティビティと <xref:System.ServiceModel.Activities.SendReply> アクティビティは、要求/応答メッセージ パターンをモデル化するためにサーバーで一緒に使用されます。 このプロパティでは、関連付ける <xref:System.ServiceModel.Activities.Send> アクティビティを指定します。 デザイナーでは、<xref:System.ServiceModel.Activities.SendReply> アクティビティを作成した <xref:System.ServiceModel.Activities.Send> アクティビティに自動的にバインドされるため、このプロパティを編集することはできません。 |
| <xref:System.ServiceModel.Activities.SendReply.Content%2A> | False | 受信するメッセージまたはパラメーターの内容を指定します。 <xref:System.ServiceModel.Activities.ReceiveMessageContent> アクティビティまたは <xref:System.ServiceModel.Activities.ReceiveParametersContent> アクティビティを指定できます。 このプロパティを編集するには、プロパティグリッドで**コンテンツ**フィールドの横にある省略記号ボタンをクリックするか、 **Receive**アクティビティデザイナー画面で **[コンテンツ]** ラベルの横にある **[定義]** ボタンをクリックします。 どちらの場合も、 **[コンテンツ定義]** ダイアログボックスが表示されます。 このボックスの使用方法の詳細については、「[[コンテンツ定義] ダイアログボックス](../workflow-designer/content-definition-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A> | False | ワークフロー内のこの <xref:System.ServiceModel.Activities.CorrelationInitializer> アクティビティを構成する複数の <xref:System.ServiceModel.Activities.CorrelationHandle> オブジェクトを初期化する <xref:System.ServiceModel.Activities.Receive> オブジェクトのコレクションを指定します。 プロパティグリッドの [<xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A>] プロパティの横にある省略記号ボタンをクリックして、 **[関連付け初期化子の追加]** ダイアログボックスを開きます。 このボックスの使用方法の詳細については、「[ [CorrelationInitializers の追加] ダイアログボックス](../workflow-designer/add-correlationinitializers-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.SendReply.Action%2A> | False | メッセージのアクション ヘッダーを指定します。 明示的に設定されていない場合、その値の既定値は次のようになります。<br /><br /> <strong>https://tempuri.org/{service コントラクト名前空間}/{サービスコントラクト名}/{操作名}</strong> |
| <xref:System.ServiceModel.Activities.SendReply.PersistBeforeSend%2A> | False | 応答メッセージを送信する前にワークフロー サービス インスタンスを永続化するかどうかを指定します。 既定値は **false** です。 |

## <a name="see-also"></a>関連項目

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Receive](../workflow-designer/receive-activity-designer.md)
- [Send](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)
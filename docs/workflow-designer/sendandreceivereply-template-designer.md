---
title: ワークフローデザイナー-SendAndReceiveReply テンプレートデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.SendAndReceiveReply.UI
- System.ServiceModel.Activities.ReceiveReply.UI
ms.assetid: 818a8c84-6593-416d-b016-1d91b85ffb68
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d7c552e8bb94ed9035f25bdd40b7944458e61a11
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649959"
---
# <a name="sendandreceivereply-template-designer"></a>SendAndReceiveReply テンプレート デザイナー

**Sendandreceivereply**テンプレートは、事前に構成された一連の <xref:System.ServiceModel.Activities.Send> と <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティを作成するために使用されます。 アクティビティは <xref:System.Activities.Statements.Sequence> アクティビティの一部であり、クライアントでの要求/応答メッセージ交換パターンの一部として関連付けられています。

## <a name="the-sendandreceivereply-template"></a>SendAndReceiveReply テンプレート

**Sendandreceivereply**テンプレートを追加するには、<xref:System.Activities.Statements.Sequence> アクティビティ内の <xref:System.ServiceModel.Activities.Send> と <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティを作成する以外に、次の3つの操作を行います。

- @No__t_2 アクティビティの <xref:System.ServiceModel.Activities.Send.OperationName%2A> および <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> プロパティを構成します。

- <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> アクティビティの <xref:System.ServiceModel.Activities.ReceiveReply> プロパティを <xref:System.ServiceModel.Activities.Send> アクティビティにバインドする。

- 親アクティビティに、変数として <xref:System.ServiceModel.Activities.CorrelationHandle> を作成する。

### <a name="use-the-sendandreceivereply-template-designer"></a>SendAndReceiveReply テンプレートデザイナーを使用する

**[ツールボックス]** の **[メッセージング]** カテゴリにある**sendandreceivereply**アクティビティデザイナーにアクセスします。 **Sendandreceivereply**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所でワークフローデザイナー画面にドロップできます。 アクティビティデザイナーを削除すると、 **send**アクティビティデザイナーと、 **Receivereplyforsend**デザイナーで構成できる関連 <xref:System.ServiceModel.Activities.ReceiveReply> を使用して構成できる <xref:System.ServiceModel.Activities.Send> アクティビティが作成されます。

**送信**デザイナーを使用して <xref:System.ServiceModel.Activities.Send> アクティビティを構成する方法の詳細については、「 [send](../workflow-designer/send-activity-designer.md)」を参照してください。

### <a name="properties-of-receivereply"></a>ReceiveReply のプロパティ

次の表は、<xref:System.ServiceModel.Activities.ReceiveReply> のプロパティと、デザイナーでのそれらの使用方法を示しています。 これらのプロパティは、プロパティグリッドで編集できます。また、ワークフローデザイナーサーフェイスで編集することもできます。

| プロパティ名 | 必要 | 使用方法 |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | False | <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティの省略可能な表示名。 既定値は、ReceiveReplyForSend です。<br /><br /> フレンドリ <xref:System.Activities.Activity.DisplayName%2A> に既定値以外の値を使用することは、厳密には必須ではありませんが、このような値を使用することをお勧めします。 |
| <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> | True | この <xref:System.ServiceModel.Activities.Send> アクティビティと関連付けられる <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティへの参照。 このプロパティを**null**にすることはできません。 <xref:System.ServiceModel.Activities.Send> アクティビティと <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティは、要求/応答メッセージ パターンをモデル化するためにクライアントで一緒に使用されます。 このプロパティでは、関連付ける <xref:System.ServiceModel.Activities.Send> アクティビティを指定します。 デザイナーでは、<xref:System.ServiceModel.Activities.ReceiveReply> アクティビティを作成した <xref:System.ServiceModel.Activities.Send> アクティビティに自動的にバインドされるため、このプロパティを編集することはできません。 |
| <xref:System.ServiceModel.Activities.ReceiveReply.Content%2A> | False | 受信するメッセージまたはパラメーターの内容を指定します。 <xref:System.ServiceModel.Activities.ReceiveMessageContent> アクティビティまたは <xref:System.ServiceModel.Activities.ReceiveParametersContent> アクティビティを指定できます。 このプロパティを編集するには、プロパティグリッドで**コンテンツ**フィールドの横にある省略記号ボタンをクリックするか、 **Receive**アクティビティデザイナー画面で **[コンテンツ]** ラベルの横にある **[定義]** をクリックします。 どちらの場合も、 **[コンテンツ定義]** ダイアログボックスが表示されます。 このボックスの使用方法の詳細については、「[[コンテンツ定義] ダイアログボックス](../workflow-designer/content-definition-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.ReceiveReply.CorrelationInitializers%2A> | False | ワークフロー内のこの <xref:System.ServiceModel.Activities.CorrelationInitializer> アクティビティを構成する複数の <xref:System.ServiceModel.Activities.CorrelationHandle> オブジェクトを初期化する <xref:System.ServiceModel.Activities.Receive> オブジェクトのコレクションを指定します。 プロパティグリッドの [<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>] プロパティの横にある省略記号ボタンをクリックして、 **[関連付け初期化子の追加]** ダイアログボックスを開きます。 このボックスの使用方法の詳細については、「 [CorrelationInitializers の追加」ダイアログボックス](../workflow-designer/add-correlationinitializers-dialog-box.md)を参照してください。 |
| <xref:System.ServiceModel.Activities.ReceiveReply.Action%2A> | False | メッセージのアクション ヘッダーを指定します。 明示的に設定されていない場合、その値の既定値は次のようになります。<br /><br /> <strong>https://tempuri.org/{service コントラクト名前空間}/{サービスコントラクト名}/{操作名}。</strong> |

## <a name="see-also"></a>関連項目

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Receive](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Send](../workflow-designer/send-activity-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)
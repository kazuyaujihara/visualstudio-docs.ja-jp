---
title: ワークフローデザイナー-Receive アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Receive.UI
ms.assetid: f58d3c70-944d-4bb4-90a7-e68c103caddc
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8c9dc2a561ce424239df5ec08eb353453b831464
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650037"
---
# <a name="receive-activity-designer"></a>Receive アクティビティ デザイナー

**Receive**アクティビティデザイナーは、<xref:System.ServiceModel.Activities.Receive> アクティビティを作成および構成するために使用されます。 <xref:System.ServiceModel.Activities.Receive> アクティビティは、メッセージ (<xref:System.ServiceModel.Channels.Message>、<xref:System.IO.Stream>、<xref:System.Xml.Linq.XElement> などの組み込みの型、アプリケーション定義のデータ コントラクト、メッセージ コントラクト、またはシリアル化可能な XML クラス) を受信するアクティビティです。

## <a name="the-receive-activity"></a>Receive アクティビティ

<xref:System.ServiceModel.Activities.Receive> アクティビティでは、使用されている受信コンテンツの型に応じて、単一または複数のアイテムを受信できます。 <xref:System.ServiceModel.Activities.SendReply> アクティビティは、サービスでの要求/応答メッセージ交換パターンの一部としてメッセージを受信する <xref:System.ServiceModel.Activities.Receive> アクティビティにバインドできます。

### <a name="using-the-receive-activity-designer"></a>Receive アクティビティ デザイナーの使用

**[ツールボックス]** の **[メッセージング]** カテゴリで**Receive**アクティビティデザイナーにアクセスします。 **Receive**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所のワークフローデザイナー画面にドロップできます。 この操作により、Receive という既定の <xref:System.ServiceModel.Activities.Receive> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 @No__t_0 は、 **Receive**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

@No__t_0 アクティビティを作成して、選択した <xref:System.ServiceModel.Activities.Receive> アクティビティにバインドするには、 **Receive**アクティビティデザイナーを右クリックし、コンテキストメニューの **[SendReply の作成]** 項目をクリックします。 **SendReplyToReceive**デザイナーが表示され**ます。受信**デザイナー。 <xref:System.ServiceModel.Activities.SendReply> アクティビティは、サービスでの要求/応答メッセージ交換パターンの一部として応答メッセージを送信するアクティビティであり、 **SendReplyToReceive**デザイナーを使用して構成できます。

または、 **[ツールボックス]** の **[メッセージング]** カテゴリの**receiveandsendreply**テンプレートデザイナーを使用して、構成済みの <xref:System.ServiceModel.Activities.Receive> と <xref:System.ServiceModel.Activities.SendReply> アクティビティのペアを作成することもできます。 **Receiveandsendreply**と**SendReplyToReceive**テンプレートの使用の詳細については、「 [receiveandsendreply](../workflow-designer/receiveandsendreply-template-designer.md) 」トピックを参照してください。

### <a name="the-receive-activity-properties"></a>Receive アクティビティのプロパティ

次の表に、<xref:System.ServiceModel.Activities.Receive> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティグリッドまたはワークフローデザイナー画面で編集できます。 必須のプロパティは <xref:System.ServiceModel.Activities.Receive.OperationName%2A> プロパティのみです。

| プロパティ名 | 必要 | 使用方法 |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | False | <xref:System.ServiceModel.Activities.Receive> アクティビティの表示名を指定します。 既定値は Receive です。<br /><br /> 既定値以外の <xref:System.Activities.Activity.DisplayName%2A> の使用は必須ではありませんが、使用することをお勧めします。 |
| <xref:System.ServiceModel.Activities.Receive.OperationName%2A> | True | この <xref:System.ServiceModel.Activities.Receive> アクティビティによって実装されるサービス操作の名前を指定します。 このプロパティは **、action プロパティ**が明示的に設定されていない場合に、 **action**プロパティの既定値を構築するために使用されます。 |
| <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> | False | サービス コントラクトの名前を指定します。 このプロパティは、サービス操作を個々のサービス コントラクトにグループ化するために使用します。 同じ <xref:System.ServiceModel.Activities.Receive> を持つすべての <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> アクティビティは、同じサービス コントラクト (WSDL ポートの種類) にグループ化されます。 既定値は、最上位レベル (ルート) アクティビティの完全修飾 CLR 名です。 |
| <xref:System.ServiceModel.Activities.Receive.Content%2A> | False | 受信するメッセージまたはパラメーターの内容を指定します。 <xref:System.ServiceModel.Activities.ReceiveMessageContent> アクティビティまたは <xref:System.ServiceModel.Activities.ReceiveParametersContent> アクティビティを指定できます。 このプロパティを編集するには、プロパティグリッドの **[コンテンツ]** フィールドの横にある省略記号ボタンを選択するか、 **Receive**アクティビティデザイナー画面で**コンテンツ**ラベルの横にある **[定義...]** ボタンをクリックします。 どちらの場合も、 **[コンテンツ定義]** ダイアログボックスが表示されます。 このボックスの使用方法の詳細については、「[[コンテンツ定義] ダイアログボックス](../workflow-designer/content-definition-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> | False | <xref:System.ServiceModel.Activities.Receive> オブジェクトを持つワークフローのサービス操作における <xref:System.ServiceModel.MessageQuerySet> アクティビティ間の相関関係を指定します。 プロパティグリッドの <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> プロパティの横にある省略記号ボタンをクリックして、 **Correlateson 定義** ダイアログボックスを開きます。 このダイアログボックスの使用方法の詳細については、「[[コンテンツ定義] ダイアログボックス](../workflow-designer/content-definition-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> | False | 適切なワークフロー インスタンスにメッセージをルーティングするために使用される <xref:System.ServiceModel.Activities.CorrelationHandle> を指定します。<br /><br /> プロパティグリッドの [<xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A>] プロパティの横にある省略記号ボタンをクリックして、 **[式エディター]** ダイアログボックスを開きます。 このダイアログボックスの使用方法の詳細については、「[方法: 式エディターを使用](../workflow-designer/how-to-use-the-expression-editor.md)する」を参照してください。 |
| <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> | False | ワークフロー内のこの <xref:System.ServiceModel.Activities.CorrelationInitializer> アクティビティを構成する複数の <xref:System.ServiceModel.Activities.CorrelationHandle> オブジェクトを初期化する <xref:System.ServiceModel.Activities.Receive> オブジェクトのコレクションを指定します。 プロパティグリッドの [<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>] プロパティの横にある省略記号ボタンをクリックして、 **[関連付け初期化子の追加]** ダイアログボックスを開きます。 このボックスの使用方法の詳細については、「[ [CorrelationInitializers の追加] ダイアログボックス](../workflow-designer/add-correlationinitializers-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> | False | メッセージが既存のワークフロー インスタンスと関連付けられていない場合に、新しいワークフロー インスタンスを作成して、このメッセージを処理するかどうかを決定する値を指定します。 この値が**true**に設定されている場合、メッセージが既存のワークフローインスタンスと関連付けられていない場合に、新しいワークフローインスタンスが作成され、メッセージが処理されます。 |
| <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> | False | この <xref:System.ServiceModel.Activities.Receive> アクティビティによって実装されるサービス操作の既知の型のコレクションを指定します。 このプロパティは、<xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> に設定された <xref:System.Runtime.Serialization.DataContractSerializer> プロパティと共に使用する必要があり、 <xref:System.Xml.Serialization.XmlSerializer> が使用されている場合は無視されます。<br /><br /> プロパティグリッドの **[Knowntypes]** フィールドの横にある省略記号ボタンをクリックすると、 **[型コレクションエディター]** ダイアログボックスが表示され、関連する型を追加できます。 このボックスの使用方法の詳細については、「[[型コレクションエディター] ダイアログボックス](../workflow-designer/type-collection-editor-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A> | False | メッセージの <xref:System.Net.Security.ProtectionLevel> を指定します。<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> は認証のみを意味します。<br />2. <xref:System.Net.Security.ProtectionLevel> は、送信されるデータの整合性を確保するためにデータに署名することを意味します。<br />3. <xref:System.Net.Security.ProtectionLevel> は、データを暗号化して署名することを意味します。これは、送信されるデータの機密性と整合性を確保するのに役立ちます。 |
| <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> | False | <xref:System.ServiceModel.Activities.Receive> アクティビティによって実装されるサービス操作に使用するシリアライザーの型を指定します。 既定値は <xref:System.Runtime.Serialization.DataContractSerializer> です。この場合、ある型のインスタンスが、提供されたデータ コントラクトを使用する XML ストリームまたはドキュメントへとシリアル化または逆シリアル化されます。 XML をより厳密に制御する必要がある場合は、<xref:System.Xml.Serialization.XmlSerializer> も使用できます。 |
| <xref:System.ServiceModel.Activities.Receive.Action%2A> | False | メッセージのアクション ヘッダーを指定します。 明示的に設定されていない場合、その値の既定値は `https://tempuri.org/{service contract namespace}/{service contract name}/{operation name}` です。 |

## <a name="see-also"></a>関連項目

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Send](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)

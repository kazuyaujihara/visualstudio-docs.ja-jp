---
title: ワークフローデザイナー-Send アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Send.UI
ms.assetid: b514f2e4-767c-4b94-ac61-dd3a54d4b96d
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 86eab31b2d268475f4ae6c9fe91c9ee5b6a4e4bc
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649970"
---
# <a name="send-activity-designer"></a>Send アクティビティ デザイナー

**Send**アクティビティデザイナーは、<xref:System.ServiceModel.Activities.Send> アクティビティを作成および構成するために使用されます。

## <a name="the-send-activity"></a>Send アクティビティ

 メッセージをサービスに送信するには、<xref:System.ServiceModel.Activities.Send> アクティビティを使用します。 <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティは、クライアントでの要求/応答メッセージ交換パターンの一部としてメッセージを受信する <xref:System.ServiceModel.Activities.Send> アクティビティにバインドできます。

### <a name="using-the-send-activity-designer"></a>Send アクティビティ デザイナーの使用

**送信**アクティビティデザイナーにアクセスするには、**ツールボックス**の **[メッセージング]** カテゴリを使用します。 **Send**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所のワークフローデザイナー画面にドロップできます。 この操作により、Send という既定の <xref:System.ServiceModel.Activities.Send> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 @No__t_0 は、**送信**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

@No__t_0 アクティビティを作成し、選択した <xref:System.ServiceModel.Activities.Send> アクティビティにバインドするには、 **Send**アクティビティデザイナーを右クリックし、コンテキストメニューの **[ReceiveReply の作成]** 項目をクリックします。 **Receivereplyforsend**デザイナーは、次の**ように表示されます。送信**デザイナー。 <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティは、クライアントでの要求/応答メッセージ交換パターンの一部としてメッセージを受信するアクティビティであり、 **Receivereplyforsend**デザイナーを使用して構成できます。

または、 **[ツールボックス]** の **[メッセージング]** カテゴリの**sendandreceivereply**テンプレートデザイナーを使用して、構成済みの <xref:System.ServiceModel.Activities.Send> と <xref:System.ServiceModel.Activities.ReceiveReply> アクティビティのペアを作成することもできます。 **Sendandreceivereply**および**Receivereplyforsend**テンプレートの使用の詳細については、「 [sendandreceivereply](../workflow-designer/sendandreceivereply-template-designer.md) 」トピックを参照してください。

### <a name="the-send-activity-properties"></a>Send アクティビティのプロパティ

次の表に、<xref:System.ServiceModel.Activities.Send> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティグリッドまたはワークフローデザイナー画面で編集できます。

| プロパティ名 | 必要 | 使用方法 |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | False | <xref:System.ServiceModel.Activities.Send> アクティビティの表示名。 既定値は Send です。 <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。 |
| <xref:System.ServiceModel.Activities.Send.OperationName%2A> | True | この <xref:System.ServiceModel.Activities.Send> アクティビティによって呼び出されるサービス操作の名前。 このプロパティは **、action プロパティ**が明示的に設定されていない場合に、 **action**プロパティの既定値を構築するために使用されます。 |
| <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> | True | 呼び出されるサービスが実装するサービス コントラクトの名前。 |
| <xref:System.ServiceModel.Activities.Send.Content%2A> | False | 受信するメッセージまたはパラメーターの内容を指定します。 <xref:System.ServiceModel.Activities.ReceiveMessageContent> アクティビティまたは <xref:System.ServiceModel.Activities.ReceiveParametersContent> アクティビティを指定できます。 このプロパティを編集するには、プロパティグリッドの **[コンテンツ]** フィールドの横にある省略記号ボタンを選択するか、 **Receive**アクティビティデザイナー画面で**コンテンツ**ラベルの横にある **[定義...]** ボタンをクリックします。 どちらの場合も、 **[コンテンツ定義]** ダイアログボックスが表示されます。 このボックスの使用方法の詳細については、「[[コンテンツ定義] ダイアログボックス](../workflow-designer/content-definition-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> | False | 適切なワークフロー インスタンスにメッセージをルーティングするために使用される <xref:System.ServiceModel.Activities.CorrelationHandle> を指定します。<br /><br /> プロパティグリッドの [<xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>] プロパティの横にある省略記号ボタンをクリックして、 **[式エディター]** ダイアログボックスを開きます。 このダイアログボックスの使用方法の詳細については、「[方法: 式エディターを使用](../workflow-designer/how-to-use-the-expression-editor.md)する」を参照してください。 |
| <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> | False | ワークフロー内のこの <xref:System.ServiceModel.Activities.CorrelationInitializer> アクティビティを構成する複数の <xref:System.ServiceModel.Activities.CorrelationHandle> オブジェクトを初期化する <xref:System.ServiceModel.Activities.Send> オブジェクトのコレクションを指定します。 プロパティグリッドの [<xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A>] プロパティの横にある省略記号ボタンをクリックして、 **[関連付け初期化子の追加]** ダイアログボックスを開きます。 このボックスの使用方法の詳細については、「[ [CorrelationInitializers の追加] ダイアログボックス](../workflow-designer/add-correlationinitializers-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> | False | この <xref:System.ServiceModel.Activities.Send> アクティビティによって呼び出されるサービス操作の既知の型のコレクション。 このプロパティは、<xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> に設定された <xref:System.Runtime.Serialization.DataContractSerializer> プロパティと共に使用する必要があります。 <xref:System.Xml.Serialization.XmlSerializer> が使用されている場合は無視されます。<br /><br /> プロパティグリッドの **[Knowntypes]** フィールドの横にある省略記号ボタンをクリックすると、 **[型コレクションエディター]** ダイアログボックスが表示され、関連する型を追加できます。<br /><br /> プロパティグリッドの **[Knowntypes]** フィールドの横にある省略記号ボタンをクリックすると、 **[型コレクションエディター]** ダイアログボックスが表示され、関連する型を追加できます。 このボックスの使用方法の詳細については、「[[型コレクションエディター] ダイアログボックス](../workflow-designer/type-collection-editor-dialog-box.md)」を参照してください。 |
| <xref:System.ServiceModel.Activities.Send.ProtectionLevel%2A> | True | メッセージの <xref:System.Net.Security.ProtectionLevel> を指定します。<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> は認証のみを意味します。<br />2. <xref:System.Net.Security.ProtectionLevel> は、送信されるデータの整合性を確保するためにデータに署名することを意味します。<br />3. <xref:System.Net.Security.ProtectionLevel> は、データを暗号化して署名することを意味します。これは、送信されるデータの機密性と整合性を確保するのに役立ちます。 |
| <xref:System.ServiceModel.Activities.Send.SerializerOption%2A> | True | <xref:System.ServiceModel.Activities.Send> アクティビティによって呼び出されるサービス操作に使用するシリアライザー。 既定値は <xref:System.Runtime.Serialization.DataContractSerializer> です。このシリアライザーは、ある型のインスタンスを、提供されたデータ コントラクトを使用する XML ストリームまたはドキュメントへとシリアル化または逆シリアル化します。 |
| <xref:System.ServiceModel.Activities.Send.Action%2A> | False | メッセージのアクション ヘッダーを指定します。 明示的に設定されていない場合、その値の既定値は、 https://tempuri.org/{service contract namespace}/{サービスコントラクト名}/{操作名} です。 <xref:System.ServiceModel.Activities.Send> アクティビティで指定した場合は、メッセージを正しく配信するために、メッセージを受信する <xref:System.ServiceModel.Activities.Receive> アクティビティに同じ値を設定する必要があります。 |
| <xref:System.ServiceModel.Activities.Send.TokenImpersonationLevel%2A> | | メッセージの受信側に許可される <xref:System.Security.Principal.TokenImpersonationLevel>。 セキュリティ偽装レベルを定義します。これは、サーバープロセスがクライアントプロセスの代わりに動作できる程度を制御します。<xref:System.Security.Principal.TokenImpersonationLevel> 偽装レベルが割り当てられていないことを示します。 <xref:System.Security.Principal.TokenImpersonationLevel> は、サーバー プロセスがクライアントの識別情報を取得することも、クライアントを偽装することもできないことを示します。 <xref:System.Security.Principal.TokenImpersonationLevel> は、サーバー プロセスがセキュリティ ID や特権などのクライアント情報を取得できるが、クライアントを偽装できないことを示します。 これは、テーブルとビューをエクスポートするデータベース製品など、独自のオブジェクトをエクスポートするサーバーで役立ちます。 サーバーは、このクライアントのセキュリティ コンテキストを使用する他のサービスを使用できなくても、取得したクライアントのセキュリティ情報を使用してアクセス検証に関する決定を行うことができます。 <xref:System.Security.Principal.TokenImpersonationLevel> は、サーバー プロセスがローカル システム上にあるクライアントのセキュリティ コンテキストを偽装できることを示します。 サーバーは、リモート システムにあるクライアントを偽装できません。 <xref:System.Security.Principal.TokenImpersonationLevel> は、サーバー プロセスがリモート システム上にあるクライアントのセキュリティ コンテキストを偽装できることを示します。 |
| <xref:System.ServiceModel.Activities.Send.Endpoint%2A> | | <xref:System.ServiceModel.Endpoint> アクティビティによるメッセージの送信先の <xref:System.ServiceModel.Activities.Send>。 このプロパティが設定されている場合は、<xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> プロパティを**null**にする必要があります。 |
| <xref:System.ServiceModel.Activities.Send.EndpointAddress%2A> | | メッセージの送信先となる <xref:System.ServiceModel.EndpointAddress>。 |
| <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> | | エンドポイント構成の名前。 このプロパティは、エンドポイントを構成ファイルで構成している場合に設定します。 このプロパティは、構成ファイルの **\<endpoint >** 要素で指定された名前に設定する必要があります。 このプロパティが設定されている場合、<xref:System.ServiceModel.Activities.Send.Endpoint%2A> プロパティは**null**にする必要があります。 |

## <a name="see-also"></a>関連項目

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Receive](../workflow-designer/receive-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)
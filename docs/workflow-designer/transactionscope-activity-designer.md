---
title: ワークフローデザイナー TransactionScope アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b5d557fb91c52c33022a161bada169d4332bac6b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649827"
---
# <a name="transactionscope-activity-designer"></a>TransactionScope アクティビティ デザイナー

**TransactionScope**アクティビティデザイナーは、<xref:System.Activities.Statements.TransactionScope> アクティビティを作成および構成するために使用されます。

## <a name="the-transactionscope-activity"></a>TransactionScope アクティビティ

<xref:System.Activities.Statements.TransactionScope> アクティビティでは、含まれているアクティビティを単一のトランザクションで実行します。 <xref:System.Activities.Statements.TransactionScope.Body%2A> アクティビティおよびトランザクションの他のすべての参加要素が正常に完了すると、トランザクションはコミットされます。

### <a name="using-the-transactionscope-activity-designer"></a>TransactionScope アクティビティ デザイナーの使用

**[ツールボックス]** の **[トランザクション]** カテゴリで、 **TransactionScope**アクティビティデザイナーにアクセスします。 **TransactionScope**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) にドロップしてワークフローデザイナー画面にドロップできます。 この操作により、TransactionScope という既定の <xref:System.Activities.Statements.TransactionScope> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 @No__t_0 値は、 **TransactionScope**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

### <a name="the-transactionscope-properties"></a>TransactionScope プロパティ

次の表に、<xref:System.Activities.Statements.TransactionScope> のプロパティと、デザイナーでのその使用方法を示します。 @No__t_0 プロパティと <xref:System.Activities.Statements.TransactionScope.Body%2A> プロパティはワークフローデザイナー画面で編集できます。 ただし、他のプロパティは、プロパティ グリッドで編集する必要があります。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TransactionScope> アクティビティの省略可能な表示名。 既定値は、TransactionScope です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|True|単一のトランザクションで実行するアクティビティを指定します。 @No__t_0 アクティビティを追加するには、"ここにアクティビティをドロップします" というヒントテキストが表示された**TransactionScope**アクティビティデザイナーの **[Body]** ボックスに、 **[ツールボックス]** からアクティビティをドロップします。|
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|True|この <xref:System.Transactions.IsolationLevel> の <xref:System.Activities.Statements.TransactionScope> を指定します。|
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|トランザクションが完了するまでの時間間隔を "00:00:00" (時:分:秒) という形式で指定します。 既定値は 1 分 (00:01:00) です。|
|[AbortInstanceOnTransactionFailure を処理します。](https://msdn.microsoft.com/library/system.activities.statements.transactionscope.abortinstanceontransactionfailure.aspx)|True|トランザクションが中止した場合にワークフローを中止する必要があるかどうかを示す値を指定します。|

## <a name="see-also"></a>関連項目

- [トランザクション](../workflow-designer/transaction-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Compensate](../workflow-designer/compensate-activity-designer.md)
- [Confirm](../workflow-designer/confirm-activity-designer.md)
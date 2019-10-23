---
title: ワークフローデザイナー-Compensate アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Compensate.UI
ms.assetid: 7347c947-bfff-4bad-becd-5cd23e7b24cd
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 65203663214e6bc82a4a7b20af9caa25bfd98ee4
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650654"
---
# <a name="compensate-activity-designer"></a>Compensate アクティビティ デザイナー

**Compensate**アクティビティデザイナーは、<xref:System.Activities.Statements.Compensate> アクティビティを作成および構成するために使用されます。

## <a name="the-compensate-activity"></a>Compensate アクティビティ

<xref:System.Activities.Statements.Compensate> アクティビティは、<xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> に含まれているアクティビティの <xref:System.Activities.Statements.CompensableActivity> を明示的に呼び出します。 <xref:System.Activities.Statements.Compensate> アクティビティが <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> の <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> 内、<xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> 内、および <xref:System.Activities.Statements.CompensableActivity> 内のいずれでも使用されていない場合は、<xref:System.Activities.Statements.Compensate.Target%2A> プロパティを指定する必要があります。

<xref:System.Activities.Statements.CompensationToken> で指定された <xref:System.Activities.Statements.Compensate.Target%2A> は、<xref:System.Activities.Statements.CompensableActivity> の <xref:System.Activities.Statements.CompensableActivity.Body%2A> が正常に完了した後に <xref:System.Activities.Statements.CompensableActivity> を明示的に確認または補正する手段を提供します。

### <a name="using-the-compensate-activity-designer"></a>Compensate アクティビティ デザイナーの使用

**Compensate**アクティビティデザイナーは、**ツールボックス**の **[トランザクション]** カテゴリにあります。 **ツールボックス**を開くには、ワークフローデザイナーの左側にある **[ツールボックス]** タブを選択します。 または、 **[表示]** メニューの **[ツールボックス]** を選択するか、 **ctrl** +**Alt** +**X**キーを押します。

**Compensate**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティが配置されている任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) にドロップしてワークフローデザイナー画面にドロップできます。 アクティビティデザイナーを削除すると、既定の <xref:System.Activities.Activity.DisplayName%2A> 補正の <xref:System.Activities.Statements.Compensate> アクティビティが作成されます。 @No__t_0 値は、 **Compensate**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

### <a name="the-compensate-properties"></a>Compensate のプロパティ

次の表に、<xref:System.Activities.Statements.CancellationScope> のプロパティと、デザイナーでのその使用方法を示します。 @No__t_0 プロパティは、プロパティグリッドまたはワークフローデザイナー画面で編集できます。 プロパティグリッドで <xref:System.Activities.Statements.Compensate.Target%2A> プロパティを編集します。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Compensate> アクティビティの表示名を指定します (省略可能)。 既定値は Compensate です。|
|<xref:System.Activities.Statements.Compensate.Target%2A>|True|この <xref:System.Activities.InArgument%601> アクティビティの <xref:System.Activities.Statements.CompensationToken> を含む <xref:System.Activities.Statements.Compensate> を指定します。|

## <a name="see-also"></a>関連項目

- [トランザクション](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Compensate アクティビティ デザイナー](../workflow-designer/compensate-activity-designer.md)
- [Confirm](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)
---
title: ワークフローデザイナー CancellationScope アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0a2fd36d81f774ca48cca170b8a4a256d73cf1f1
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650699"
---
# <a name="cancellationscope-activity-designer"></a>CancellationScope アクティビティ デザイナー

**CancellationScope**アクティビティデザイナーは、<xref:System.Activities.Statements.CancellationScope> アクティビティを作成および構成するために使用されます。

## <a name="the-cancellationscope-activity"></a>CancellationScope アクティビティ

<xref:System.Activities.Statements.CancellationScope> アクティビティを使用すると、実行のアクティビティと、そのアクティビティの取り消しロジックを指定できます。

### <a name="using-the-cancellationscope-activity-designer"></a>CancellationScope アクティビティ デザイナーの使用

**CancellationScope**アクティビティデザイナーは、 **[ツールボックス]** の **[トランザクション]** カテゴリにあります。 **ツールボックス**を開くには、ワークフローデザイナーの **[ツールボックス]** タブを選択します。 または、 **[表示]** メニューの **[ツールボックス]** を選択するか、 **ctrl** +**Alt** +**X**キーを押します。

**CancellationScope**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティが配置されている任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) ワークフローデザイナー画面にドロップできます。 **CancellationScope**アクティビティデザイナーを削除すると、CancellationScope の既定の <xref:System.Activities.Activity.DisplayName%2A> を持つ <xref:System.Activities.Statements.CancellationScope> アクティビティが作成されます。 **CancellationScope**アクティビティデザイナーのヘッダーで <xref:System.Activities.Activity.DisplayName%2A> 値を編集します。 また、プロパティグリッドの **[DisplayName]** ボックスで編集することもできます。

### <a name="the-cancellationscope-properties"></a>CancellationScope プロパティ

次の表に、<xref:System.Activities.Statements.CancellationScope> のプロパティと、デザイナーでのその使用方法を示します。 @No__t_0 プロパティはプロパティグリッドで編集できますが、他のプロパティはワークフローデザイナー画面で編集する必要があります。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.CancellationScope> アクティビティの省略可能な表示名。 既定では、CancellationScope です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.CancellationScope.Body%2A>|True|取り消しロジックの対象となるアクティビティを指定します。 @No__t_0 アクティビティを追加するには、 **CancellationScope**アクティビティデザイナーの **[Body]** ボックスに、 **[ツールボックス]** からアクティビティをドロップします。 "ここにアクティビティをドロップします" というヒントテキストを追加します。|
|<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>|True|取り消しが発生した場合に実行されるアクティビティを指定します。 @No__t_0 アクティビティを追加するには、 **CancellationScope**アクティビティデザイナーの **[CancellationHandler]** ボックスに、 **[ツールボックス]** からアクティビティをドロップします。 "ここにアクティビティをドロップします" というヒントテキストを追加します。|

## <a name="see-also"></a>関連項目

- [トランザクション](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Compensate](../workflow-designer/compensate-activity-designer.md)
- [Confirm](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)
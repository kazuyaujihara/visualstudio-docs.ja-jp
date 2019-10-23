---
title: ワークフローデザイナー-InvokeDelegate
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
author: jillre
ms.openlocfilehash: 5227d96e3fad03dd3e3309523a6d2c68a1abdc11
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650181"
---
# <a name="invokedelegate"></a>InvokeDelegate

**Invokedelegate**デザイナーは、<xref:System.Activities.Statements.InvokeDelegate> アクティビティを作成および構成するために使用されます。

## <a name="the-invokedelegate-activity"></a>InvokeDelegate アクティビティ

<xref:System.Activities.Statements.InvokeDelegate> はパブリック デリゲートを呼び出します。

### <a name="use-the-invokedelegate-activity-designer"></a>InvokeDelegate アクティビティデザイナーの使用

**ツールボックス**の **[プリミティブ]** カテゴリで、 **invokedelegate**アクティビティデザイナーにアクセスします。 **Invokedelegate**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置しているワークフローデザイナー画面 (<xref:System.Activities.Statements.Sequence> 内など) にドロップできます。 アクティビティデザイナーを削除すると、InvokeDelegate の既定の <xref:System.Activities.Activity.DisplayName%2A> を持つ <xref:System.Activities.Statements.InvokeDelegate> アクティビティが作成されます。 @No__t_0 は、 **Invokedelegate**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

### <a name="the-invokedelegate-properties"></a>InvokeDelegate プロパティ

次の表に、<xref:System.Activities.Statements.InvokeDelegate> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティグリッドで編集できます。また、ワークフローデザイナーサーフェイスで編集することもできます。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.InvokeDelegate> アクティビティの表示名。 既定値は InvokeDelegate です。<br /><br /> @No__t_0 は厳密には必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|True|アクティビティの実行時に呼び出す <xref:System.Activities.ActivityDelegate> の名前。 このプロパティは、デザイナー画面で編集でき、必須です。|
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|呼び出されたデリゲートの引数コレクション。 キーは <xref:System.Activities.ActivityDelegate> のパラメーターオブジェクトの名前であり、値は、式が評価され、対応するパラメーターオブジェクトに割り当てられる引数です。 このプロパティを設定できる **[DelegateArguments]** ダイアログボックスを表示するには、プロパティグリッドの**DelegateArguments**フィールドで、省略記号ボタンをクリックします。 引数を追加するには、 **[引数の作成]** フィールドをクリックします。|

## <a name="see-also"></a>関連項目

- [方法: ワークフロー デザイナーでアクティビティ デリゲートを定義および使用する](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)
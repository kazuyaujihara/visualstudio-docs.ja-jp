---
title: InvokeDelegate |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
caps.latest.revision: 3
author: steved0x
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: fc35aec714255b467431488936605fb37009db9d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72659005"
---
# <a name="invokedelegate"></a>InvokeDelegate

**Invokedelegate**デザイナーは、<xref:System.Activities.Statements.InvokeDelegate> アクティビティを作成および構成するために使用されます。

## <a name="the-invokedelegate-activity"></a>InvokeDelegate アクティビティ

<xref:System.Activities.Statements.InvokeDelegate> はパブリック デリゲートを呼び出します。

### <a name="using-the-invokedelegate-activity-designer"></a>InvokeDelegate アクティビティ デザイナーの使用

**Invokedelegate**アクティビティデザイナーは、**ツールボックス**の **[プリミティブ]** カテゴリにあります。 [**ツールボックス] タブ [!INCLUDE[wfd2](../includes/wfd2-md.md)]** (または、表示] メニューの **[ツールバー]** を選択すると**表示**されます。CTRL + ALT + X

**Invokedelegate**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面 (<xref:System.Activities.Statements.Sequence> 内など) にドロップできます。 この操作により、InvokeDelegate という既定の <xref:System.Activities.Statements.InvokeDelegate> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 @No__t_0 は、 **Invokedelegate**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

### <a name="the-invokedelegate-properties"></a>InvokeDelegate プロパティ

次の表に、<xref:System.Activities.Statements.InvokeDelegate> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドで編集できます。また、その一部は[!INCLUDE[wfd2](../includes/wfd2-md.md)]のデザイナー画面で編集できます。

|プロパティ名|必須|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.InvokeDelegate> アクティビティの表示名。 既定値は InvokeDelegate です。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|True|アクティビティの実行時に呼び出す <xref:System.Activities.ActivityDelegate> の名前。 このプロパティは、デザイナー画面で設定することもできます。 これは必須プロパティです。|
|<<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|呼び出されたデリゲートの引数コレクション。 キーは <xref:System.Activities.DelegateArgument> の <xref:System.Activities.ActivityDelegate> オブジェクトの名前であり、値は、式が評価され対応する <xref:System.Activities.DelegateArgument> オブジェクトに割り当てられる引数です。 プロパティグリッドで、 **[DelegateArguments]** フィールドの省略記号ボタンをクリックすると、このプロパティを設定するための **[DelegateArguments]** ダイアログボックスが表示されます。 引数を追加するには、 **[引数の作成]** フィールドをクリックします。|

## <a name="see-also"></a>関連項目

- [方法: ワークフロー デザイナーでアクティビティ デリゲートを定義および使用する](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)
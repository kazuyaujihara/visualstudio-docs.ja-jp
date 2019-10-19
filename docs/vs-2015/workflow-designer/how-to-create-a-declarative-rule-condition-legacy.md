---
title: '方法: 宣言型の規則条件を作成する (レガシ) |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- declarative rule conditions
- condition statements, declarative rule conditions
- Rule Condition Editor dialog box
ms.assetid: 804b6129-c433-408f-a424-46987967730c
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d3a15aad987e46edb58da3560828c70571df2227
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663416"
---
# <a name="how-to-create-a-declarative-rule-condition-legacy"></a>方法: 宣言的ルール条件を作成する (レガシ)
このトピックでは、[!INCLUDE[wfd1](../includes/wfd1-md.md)] または [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] を対象とする従来の [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)]を使用してルール条件を宣言する方法について説明します。

 条件ステートメントは、 **True**または**False**に評価されます。 宣言型のルール条件とは、[[ルール条件エディター] ダイアログボックス (レガシ)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)を使用して作成され、ワークフローと共に XML として格納される condition ステートメントです。 複数の述語を結合したブール値演算とワークフロー ステートとを比較する述語を含めることができます。

 宣言的ルール条件は、次のような Windows Workflow Foundation 事前定義アクティビティで使用されます。

- [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)

- [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)

- [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)

- [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)

- [(Sequentialworkflowactivity)](http://go.microsoft.com/fwlink?LinkID=65040)

- [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)

### <a name="to-create-a-declarative-rule-condition-using-the-rule-condition-editor"></a>ルール条件エディタを使って宣言的ルール条件を作成するには

1. アクティビティの **[プロパティ]** ウィンドウで、アクティビティに応じて **[条件]** **プロパティまたは**[期間] プロパティをクリックします。

2. プロパティの一覧から **[宣言型の規則の条件]** を選択します。

3. **[条件]** または 発生する **[条件]** プロパティを展開します。

4. **[Conditionname]** プロパティをクリックします。

5. **[Conditionname]** の省略記号 **[...]** をクリックして、 **[条件の選択]** ダイアログボックスを開きます。

6. **[新しい条件]** をクリックして、 **[ルール条件エディター]** ダイアログボックスを開きます。

7. **[条件]** ボックスに条件の式を入力します。

     条件式の作成方法の詳細については、「[[ルール条件エディター] ダイアログボックス (レガシ)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)」を参照してください。

8. 条件式の作成が終了したら、 **[OK]** をクリックしてダイアログボックスを閉じ、名前が割り当てられたルール条件を作成します。

     **[条件の選択**] ダイアログボックスが表示されます。

     **[条件の選択**] ダイアログボックスの使用方法の詳細については、「 [[条件の選択] ダイアログボックス (レガシ)](../workflow-designer/select-condition-dialog-box-legacy.md)」を参照してください。

## <a name="see-also"></a>参照
 [ [While アクティビティ](http://go.microsoft.com/fwlink?LinkID=65091)ルール条件エディター] ダイアログボックス[を使用](http://go.microsoft.com/fwlink?LinkID=65080)して、 [IfElseBranchActivity アクティビティ](http://go.microsoft.com/fwlink?LinkID=65075)を使用して[Conditionedactivitygroup を使用する](http://go.microsoft.com/fwlink?LinkID=65066)[従来のワークフローアクティビティ](../workflow-designer/legacy-workflow-activities.md) [(レガシ)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)[ワークフローの条件を使用し](http://go.microsoft.com/fwlink?LinkID=65009)た[[条件の選択] ダイアログボックス (レガシ)](../workflow-designer/select-condition-dialog-box-legacy.md)
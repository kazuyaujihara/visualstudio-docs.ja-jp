---
title: '[ルール条件エディター] ダイアログボックス (レガシ) |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Rules.Design.RuleConditionDialog.UI
helpviewer_keywords:
- Rule Condition dialog box
ms.assetid: c7ca8be9-de31-4a64-939c-4d53a50d5e29
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 93aef1e4466bd88d87ebce71161dcd1665178317
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663348"
---
# <a name="rule-condition-editor-dialog-box-legacy"></a>[ルール条件エディター] ダイアログ ボックス (レガシ)
このトピックでは、従来の [!INCLUDE[wfd1](../includes/wfd1-md.md)] の **[ルール条件エディター]** ダイアログボックスの使用方法について説明します。 [!INCLUDE[wfd2](../includes/wfd2-md.md)] または [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] を対象とする必要がある場合は、従来の[!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)]を使用します。

 **[ルール条件エディター]** ダイアログボックスを使用して、宣言型の規則の条件を作成および変更します。 これらのルール条件は、Windows Workflow Foundation の事前定義アクティビティにプロパティとして公開されています。

- [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)

- [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)

- [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)

- [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)

- [(Sequentialworkflowactivity)](http://go.microsoft.com/fwlink?LinkID=65040)

- [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)

  **[ルール条件エディター]** ダイアログボックスにアクセスするには、 [[条件の選択] ダイアログボックス (レガシ)](../workflow-designer/select-condition-dialog-box-legacy.md)を使用します。

  次の表では、 **[ルール条件エディター]** ダイアログボックスのユーザーインターフェイス (UI) 要素について説明します。

|UI 要素|説明|
|----------------|-----------------|
|**フィルター**|ルールの条件式を入力します。|
|**わかりました**|これをクリックすると、ルール条件が保存されます。|

## <a name="entering-condition-expressions"></a>条件式の入力
 条件式は、テキストとして入力します。 これは、「」と入力することができ**ます。** エディターを使用して、IntelliSense に似たメニューを使用して、ワークフローで使用されるフィールド、プロパティ、およびメソッドを参照します。 または、ワークフローのメンバ名を直接入力することもできます。 条件には、AND、OR、NOT といった論理演算子を追加することもできます。 述語も追加できます。 述語は、バイナリ演算子と 2 つのオペランドから成ります。 サポートされているバイナリ演算子は、 **==** 、 **>** 、 **\<** 、 **>=** 、および **<=** です。 サポートされているオペランドは、定数値、算術関数、スコープ付きパブリック メンバです。

 比較の種類を指定して、 **null**または空の文字列と比較することができます。 複合型を含む変数でメンバに対する呼び出しをネストすることができます (たとえば `this.Address.State == "WA"`)。

 ルール条件エディタは、次の演算子をサポートします。

- 関係演算子 : ==、=、!=

- 比較演算子: <、\< =、>、> =

- 算術演算子 : +、-、*、/、MOD

- 論理演算子:また、& &、または&#124; &#124;、

- ビットごとの演算子: &、&#124;

  式演算子の優先順位は、C# 演算子の優先順位規則に従います。

  ルール条件エディタは、次の数式をサポートします。

  this.i == 1D (1.0 に解決)

  this.i == 1E1 (10.0 に解決)

  this.i == 1L (long として解決)

  this.i == 1M (decimal として解決)

  this.i == 1F (single として解決)

  this.i == 1U (unsigned int として解決)

  条件の詳細については、「[ワークフローでの条件の使用](http://go.microsoft.com/fwlink?LinkID=65009)」を参照してください。

## <a name="see-also"></a>関連項目
 [IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033) [conditionedactivitygroup](http://go.microsoft.com/fwlink?LinkID=65017) [replicatoractivity](http://go.microsoft.com/fwlink?LinkID=65039) [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)の[[条件の選択] ダイアログボックス (レガシ)](../workflow-designer/select-condition-dialog-box-legacy.md) [ワークフローの条件を使用する](http://go.microsoft.com/fwlink?LinkID=65009) [Windows Workflow のレガシデザイナーFoundation UI のヘルプ](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)
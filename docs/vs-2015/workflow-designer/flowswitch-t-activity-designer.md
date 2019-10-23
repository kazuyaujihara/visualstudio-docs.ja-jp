---
title: FlowSwitch &lt;T &gt; アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Core.Presentation.FlowSwitchLink.UI
- System.Activities.Statements.FlowSwitch`1.UI
- System.Activities.Core.Presentation.FlowSwitchLink`1.UI
- System.Activities.Core.Presentation.FlowSwitchLinkIdentifier.UI
ms.assetid: 5b9c5afe-7499-4ee8-8c33-28aff14bde07
caps.latest.revision: 4
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 27abb660766a7c04742eca221432af19f05f0d28
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656640"
---
# <a name="flowswitchlttgt-activity-designer"></a>FlowSwitch &lt;T &gt; アクティビティデザイナー
<xref:System.Activities.Statements.FlowSwitch%601> アクティビティは、3 つ以上の代替分岐が必要な場合に、一致条件に基づいて制御フローの分岐を提供する条件ノードです。 フローの分岐に必要なパスが 2 つのみである場合は、代わりに <xref:System.Activities.Statements.FlowDecision> アクティビティを使用します。

## <a name="the-flowswitcht-activity"></a>FlowSwitch \<T > アクティビティ
 @No__t_0 アクティビティには、評価時に*t*型 (ジェネリックパラメーターで指定) の値を返す <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> が含まれています。 アクティビティには、<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> のセットも含まれます。これは、この評価の想定される結果から、<xref:System.Activities.Statements.FlowNode> オブジェクトへの一意のマッピングを指定します。 実行される <xref:System.Activities.Statements.FlowNode> は、 *t*型のオブジェクトが評価された <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> の値と一致するものです。 <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> case は、一致が取得されない case に対して (必要に応じて) 提供できます。

### <a name="using-the-flowswitcht-activity-designer"></a>FlowSwitch \<T > アクティビティデザイナーの使用
 **FlowSwitch \<T >** アクティビティデザイナーは、 **[ツールボックス]** の **[フローチャート]** カテゴリにあります。このカテゴリにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)] の左側にある **[ツールボックス]** タブをクリックします (または、 **[ツールバー]** を選択します)。 **[表示]** メニューから、または CTRL + ALT + X キーを押します)。

 **FlowSwitch \<T >** アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、 **Flowchart**アクティビティデザイナー内の [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 表示される **[型の選択**] ウィンドウを使用して、<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> の評価から取得した型 (コードに関連付けられている、ジェネリックパラメーターによって <xref:System.Activities.Statements.FlowSwitch%601>) を指定します。 この手順では、<xref:System.Activities.Statements.Flowchart> アクティビティ内に**Switch**という名前の <xref:System.Activities.Statements.FlowSwitch%601> アクティビティを作成します。 @No__t_0 を **[プロパティ]** ウィンドウの **[式]** ボックスに入力するには、ヒントテキストに "VB の式を入力してください" と表示されている場所をクリックします。

 マウスポインターを**FlowSwitch \<T >** アクティビティデザイナーを使用すると、<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> をリンクして端の周囲に表示される四角形ハンドルが表示されます。 **FlowSwitch < T \>** アクティビティデザイナー、およびその他のアクティビティデザイナーを**フローチャート**にドラッグすると、それらが表す <xref:System.Activities.Activity> オブジェクトを相互にリンクして、実行の順序を指定できます。 @No__t_1 に関連付けられているいずれかの <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> を作成するには、 **FlowSwitch \<T >** の境界上にあるいずれかのケースハンドルをクリックして (マウスボタンを押したまま)、右上にある同様の方法で表示されるハンドルのいずれかにドラッグします。マウスポインターがデザイナーの上に移動したときの変換先アクティビティ。 マウスボタンを放すと、 **FlowSwitch \<T >** の矢印が変換先デザイナーに表示され、このケースが示されます。 このケースの既定値は矢印に表示され、 **[プロパティ]** ウィンドウの **[ケース]** ボックスで編集できます。

### <a name="the-flowswitcht-properties"></a>FlowSwitch \<T > プロパティ
 次の表に、<xref:System.Activities.Statements.FlowSwitch%601> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドまたはデザイナー画面で編集できます。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>|True|実行パスのどの <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> に切り替えるかを決定するために評価される式を指定します。|
|<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>|False|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> の評価によって得られる可能性のある結果から、<xref:System.Activities.Statements.FlowNode> オブジェクトのセットへの一意のマッピングを指定します。|
|<xref:System.Activities.Statements.FlowSwitch%601.Default%2A>|True|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> の評価が、<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> オブジェクトに含まれる値のいずれにも一致しない場合のマッピングを指定します。|

## <a name="see-also"></a>参照
 [フロー](../workflow-designer/flowchart-activity-designers.md) [チャートフローチャート](../workflow-designer/flowchart-activity-designer.md) [flowdecision](../workflow-designer/flowdecision-activity-designer.md)
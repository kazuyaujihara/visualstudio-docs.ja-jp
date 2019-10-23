---
title: WriteLine アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c4f656578526879774e698523239d5a9b2b14ccd
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72657524"
---
# <a name="writeline-activity-designer"></a>WriteLine アクティビティ デザイナー
**WriteLine**アクティビティデザイナーは、<xref:System.Activities.Statements.WriteLine> アクティビティを作成および構成するために使用されます。

## <a name="the-writeline-activity"></a>WriteLine アクティビティ
 <xref:System.Activities.Statements.WriteLine> アクティビティは、指定された <xref:System.IO.TextWriter> オブジェクトにテキストを書き込みます。 <xref:System.IO.TextWriter> を指定しない場合、<xref:System.Activities.Statements.WriteLine> はテキストをコンソールに書き込みます。

### <a name="using-the-writeline-activity-designer"></a>WriteLine アクティビティ デザイナーの使用
 **WriteLine**アクティビティデザイナーは、**ツールボックス**の **[プリミティブ]** カテゴリにあります。このカテゴリにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)] の **[ツールボックス]** タブをクリックします (または、 **[表示]** メニューの **[ツールバー]** を選択します)。CTRL + ALT + X)

 **WriteLine**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) に [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 この操作により、WriteLine という既定の <xref:System.Activities.Statements.WriteLine> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 @No__t_0 は、 **WriteLine**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

### <a name="the-writeline-properties"></a>WriteLine プロパティ
 次の表に、<xref:System.Activities.Statements.WriteLine> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドで編集できます。また、一部のプロパティは、[!INCLUDE[wfd2](../includes/wfd2-md.md)]のデザイナー画面で編集できます。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.WriteLine> アクティビティの表示名。 既定値は WriteLine です。 <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.WriteLine.Text%2A>|False|書き込むテキスト。 プロパティを設定するには、 **WriteLine**アクティビティデザイナーまたはプロパティグリッドの**テキスト**ボックスに Visual Basic 式を入力します。|
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|False|<xref:System.IO.TextWriter> による <xref:System.Activities.Statements.WriteLine> の書き込み先の <xref:System.Activities.Statements.WriteLine.Text%2A>。 既定はコンソールです。|

## <a name="see-also"></a>参照
 [プリミティブ](../workflow-designer/primitives-activity-designers.md)による[遅延](../workflow-designer/delay-activity-designer.md) [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)の[割り当て](../workflow-designer/assign-activity-designer.md)
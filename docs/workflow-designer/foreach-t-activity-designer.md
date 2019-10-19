---
title: ワークフローデザイナー-ForEach &lt;T &gt; アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ForEach`1.UI
ms.assetid: 67097b3a-fcf5-4a72-beb1-2c7784151a86
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: faf2f62c482deac963f597c9861fbf2acedc945c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650397"
---
# <a name="foreachlttgt-activity-designer"></a>ForEach &lt;T &gt; アクティビティデザイナー

<xref:System.Activities.Statements.ForEach%601> アクティビティは、指定した <xref:System.Activities.Statements.ForEach%601.Body%2A> コレクション内の各項目に対して、<xref:System.Activities.Statements.ForEach%601.Values%2A> に含まれるアクティビティを実行します。

## <a name="foreacht-properties-in-the-workflow-designer"></a>ForEach < T \> のプロパティワークフローデザイナー

次の表に、最も役に立つ <xref:System.Activities.Statements.ForEach%601> アクティビティのプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.ForEach%601> アクティビティの表示名。 既定値は ForEach < Int32 \> です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.ForEach%601.Values%2A>|True|反復処理を行う項目のコレクション。 @No__t_0 を設定するには、 **ForEach < t \>** アクティビティデザイナーまたはプロパティグリッドの **[値]** ボックスに Visual Basic 式を入力します。|
|*TypeArgument*|True|ジェネリックパラメーター *t*によって指定された <xref:System.Activities.Statements.ForEach%601.Values%2A> コレクション内の項目の型。既定では、 *Typeargument*は**Int32**に設定されています。 型を変更するには、プロパティグリッドの*Typeargument*コンボボックスの値を変更します。|

既定では、ループ反復子には**item**という名前が付けられます。 反復子変数の名前は、<xref:System.Activities.Statements.ForEach%601> アクティビティ デザイナーで変更できます。 ループ反復子は、<xref:System.Activities.Statements.ForEach%601> アクティビティの子の式で使用できます。

## <a name="see-also"></a>関連項目

- [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)
- [制御フロー](../workflow-designer/control-flow-activity-designers.md)
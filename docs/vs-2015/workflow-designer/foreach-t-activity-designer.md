---
title: ForEach&lt;T&gt;アクティビティ デザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ForEach`1.UI
ms.assetid: 67097b3a-fcf5-4a72-beb1-2c7784151a86
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 97732b92c5a90334917ad4e74667f88d605b647d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62943291"
---
# <a name="foreachlttgt-activity-designer"></a>ForEach&lt;T&gt;アクティビティ デザイナー
<xref:System.Activities.Statements.ForEach%601> アクティビティは、指定した <xref:System.Activities.Statements.ForEach%601.Body%2A> コレクション内の各項目に対して、<xref:System.Activities.Statements.ForEach%601.Values%2A> に含まれるアクティビティを実行します。  
  
## <a name="foreacht-properties-in-the-workflow-designer"></a>ForEach\<T > のワークフロー デザイナーでのプロパティ  
 次の表に、最も役に立つ <xref:System.Activities.Statements.ForEach%601> アクティビティのプロパティと、デザイナーでのその使用方法を示します。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.ForEach%601> アクティビティの表示名。 既定値は ForEach\<Int32 > です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|  
|<xref:System.Activities.Statements.ForEach%601.Values%2A>|True|反復処理を行う項目のコレクション。 設定する、 <xref:System.Activities.Statements.ForEach%601.Values%2A>、タイプ a[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]内の式、**値**ボックスに、 **ForEach\<T >** アクティビティ デザイナーまたはプロパティ グリッドで。|  
|*TypeArgument*|True|内の項目の種類、<xref:System.Activities.Statements.ForEach%601.Values%2A>ジェネリック パラメーターで指定されたコレクション*T*します。既定では、 *TypeArgument*に設定されている**Int32**します。 型を変更するには、値を変更、 *TypeArgument*プロパティ グリッドのコンボ ボックス。|  
  
 既定では、ループの反復子が名前付き**項目**します。 反復子変数の名前は、<xref:System.Activities.Statements.ForEach%601> アクティビティ デザイナーで変更できます。 ループ反復子は、<xref:System.Activities.Statements.ForEach%601> アクティビティの子の式で使用できます。  
  
## <a name="see-also"></a>関連項目  
 [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)   
 [制御フロー](../workflow-designer/control-flow-activity-designers.md)
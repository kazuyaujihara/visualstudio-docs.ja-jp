---
title: 制御フロー アクティビティ デザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: ba74af23-5398-4e62-bd90-c50612e3bfef
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 25f8db1f6d14692538fe7f61ed2f9dbd37e0bd29
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "59002775"
---
# <a name="control-flow-activity-designers"></a>制御フロー アクティビティ デザイナー
[!INCLUDE[wfd1](../includes/wfd1-md.md)]には、システムによって提供されるさまざまなアクティビティが用意されており、これらを、ワークフローの構築時に使用できます。 このセクションでは、ワークフロー内のフローの制御を目的とした、システムによって提供されるアクティビティを紹介します。 次のトピックでは、これらのアクティビティについて説明し、その使用方法についてのガイドラインを示します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [DoWhile](../workflow-designer/dowhile-activity-designer.md)  
 指定した条件が評価されるまでに本体内に 1 回以上含まれるアクティビティを実行します。 **true**します。  
  
 [ForEach\<T>](foreach-t-activity-designer.md)  
 指定したコレクション内の各項目に対して、本文に含まれるアクティビティを実行します。  
  
 [If](../workflow-designer/if-activity-designer.md)  
 条件を評価し、その評価の結果に応じてアクティビティを実行します。  
  
 [Parallel](../workflow-designer/parallel-activity-designer.md)  
 一連の子アクティビティを同時に実行します。  
  
 [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)  
 コレクションの要素を列挙し、コレクションの各要素に対して埋め込みステートメントを並列実行します。  
  
 [Pick](../workflow-designer/pick-activity-designer.md)  
 イベント ベースのフロー制御を提供するイベントに応答して、複数の分岐の 1 つを実行します。  
  
 [PickBranch](../workflow-designer/pickbranch-activity-designer.md)  
 <xref:System.Activities.Statements.Pick> アクティビティ内で実行パスを提供します。  
  
 [Sequence](../workflow-designer/sequence-activity-designer.md)  
 順番に実行される、子アクティビティの順序付きコレクションが含まれます。  
  
 [Switch\<T>](switch-t-activity-designer.md)  
 指定した式を評価し、その評価から得られた値と一致する関連付けられたキーを持つアクティビティのコレクションから、特定のアクティビティを実行します。  
  
 [While](../workflow-designer/while-activity-designer.md)  
 指定された条件の評価中に、その本体に含まれるアクティビティを実行します。 **true**します。  
  
## <a name="reference"></a>参照  
 <xref:System.Activities.Activity>  
  
 <xref:System.Activities.Statements.DoWhile>  
  
 <xref:System.Activities.Statements.ForEach%601>  
  
 <xref:System.Activities.Statements.If>  
  
 <xref:System.Activities.Statements.Parallel>  
  
 <xref:System.Activities.Statements.ParallelForEach%601>  
  
 <xref:System.Activities.Statements.Pick>  
  
 <xref:System.Activities.Statements.PickBranch>  
  
 <xref:System.Activities.Statements.Sequence>  
  
 <xref:System.Activities.Statements.Switch%601>  
  
 <xref:System.Activities.Statements.While>  
  
## <a name="related-sections"></a>関連項目  
 他の種類のアクティビティ デザイナーについては、次のトピックを参照してください。  
  
 [アクティビティ デザイナーの使用](../workflow-designer/using-the-activity-designers.md)  
  
 [フローチャート](../workflow-designer/flowchart-activity-designers.md)  
  
 [Messaging](../workflow-designer/messaging-activity-designers.md)  
  
 [ランタイム](../workflow-designer/runtime-activity-designers.md)  
  
 [Primitives](../workflow-designer/primitives-activity-designers.md)  
  
 [トランザクション](../workflow-designer/transaction-activity-designers.md)  
  
 [コレクション](../workflow-designer/collection-activity-designers.md)  
  
 [エラー処理](../workflow-designer/error-handling-activity-designers.md)  
  
## <a name="external-resources"></a>外部リソース  
 [アクティビティ デザイナーの使用](../workflow-designer/using-the-activity-designers.md)
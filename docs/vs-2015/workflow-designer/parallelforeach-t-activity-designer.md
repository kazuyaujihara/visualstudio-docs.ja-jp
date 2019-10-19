---
title: ParallelForEach &lt;T &gt; アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ParallelForEach`1.UI
ms.assetid: e93a4843-aef2-4d3e-9a0a-a2d3d1411aa7
caps.latest.revision: 9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 4c659e941a8503a0d5ff601fea23fcec69b2bbcf
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672612"
---
# <a name="parallelforeachlttgt-activity-designer"></a>ParallelForEach &lt;T &gt; アクティビティデザイナー
<xref:System.Activities.Statements.ParallelForEach%601> アクティビティでは、コレクションの要素を列挙し、コレクションの各要素に対して埋め込みステートメントを並列的に (同じスレッドで非同期的に) 実行します。 このフロー制御アクティビティは、その子アクティビティがアイドル状態になると予想される場合に、<xref:System.Activities.Statements.Sequence> アクティビティの代わりに使用します。

 <xref:System.Activities.Statements.ParallelForEach%601> アクティビティには、ユーザーによって指定された <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> 式を保持する [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] プロパティがあります。 このプロパティは、各分岐の完了後に、<xref:System.Activities.Statements.ParallelForEach%601> アクティビティによって評価されます。 **True**と評価された場合、<xref:System.Activities.Statements.ParallelForEach%601> のアクティビティは、他の分岐を実行せずに完了します。 @No__t_0 が**true**と評価されない場合、そのすべての子アクティビティが完了した時点で <xref:System.Activities.Statements.ParallelForEach%601> アクティビティが完了します。

## <a name="the-parallelforeacht-activity"></a>ParallelForEach \<T > アクティビティ
 <xref:System.Activities.Statements.ParallelForEach%601> はそれ自体の値を列挙し、列挙した値ごとに <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> をスケジュールします。 スケジュールされるのは <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> のみです。 本文の実行方法は、<xref:System.Activities.Statements.ParallelForEach%601.Body%2A> がアイドル状態になるかどうかによって異なります。

 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> がアイドル状態にならない場合は、スケジュールされたアクティビティがスタックとして扱われるため、逆の順序で実行されます。つまり、最後にスケジュールされたアクティビティが最初に実行されます。 たとえば、{1,2,3,4}in <xref:System.Activities.Statements.ParallelForEach%601> のコレクションがあり、 **WriteLine**を本文として使用して値を書き込む場合などです。コンソールには、4、3、2、1が出力されています。 これは、 **writeline**がアイドル状態にならず、4つの**writeline**アクティビティがスケジュールされた後で、スタック動作 (最初は最後の出力) を使用して実行されたためです。

 ただし、<xref:System.Activities.Statements.ParallelForEach%601.Body%2A> アクティビティや <xref:System.ServiceModel.Activities.Receive> アクティビティのように、アイドル状態になる可能性のあるアクティビティが <xref:System.Activities.Statements.Delay> に含まれている場合は、 それぞれのアクティビティが完了するまで待機する必要はありません。 <xref:System.Activities.Statements.ParallelForEach%601> は、スケジュールされている次の本文アクティビティに進み、実行を試みます。 そのアクティビティもアイドル状態になる場合は、<xref:System.Activities.Statements.ParallelForEach%601> が、さらに次の本文アクティビティに進みます。

### <a name="using-the-parallelforeacht-activity-designer"></a>ParallelForEach \<T > アクティビティデザイナーの使用
 **Parallelforeach \<T >** アクティビティデザイナーは、**ツールボックス**の **[制御フロー]** カテゴリにあります。このカテゴリにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)] の左側にある **[ツールボックス]** タブをクリックします (または、 **ツールバー**の **[表示]** メニュー、または CTRL + ALT + X キー)

 **Parallelforeach \<T >** アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティデザイナーを通常配置している [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面の任意の場所 ( **Sequence**アクティビティデザイナー内など) にドロップできます。 @No__t_0 にドロップすると、<xref:System.Activities.Statements.ParallelForEach%601> アクティビティが作成されます。このアクティビティには、既定で、 **Parallelforeach \<Int32 >** の <xref:System.Activities.Activity.DisplayName%2A> が含まれています。

### <a name="parallelforeacht-properties-in-the-workflow-designer"></a>ParallelForEach \<T > ワークフローデザイナー内のプロパティ
 次の表に、最も役に立つ <xref:System.Activities.Statements.ParallelForEach%601> アクティビティのプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|ヘッダーのアクティビティ デザイナーの表示名を指定します。 既定値は、 **Parallelforeach \<Int32 >** です。 この値は、必要に応じて、 **[プロパティ]** グリッドで編集することも、アクティビティデザイナーのヘッダーで直接編集することもできます。|
|<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>|False|コレクション内の各項目に対して実行するアクティビティ。 @No__t_0 アクティビティを追加するには、"ここにアクティビティをドロップします" というヒントテキストが表示された**Parallelforeach \<T >** アクティビティデザイナーの **[Body]** ボックスに、[ツールボックス] からアクティビティをドロップします。|
|**TypeArgument**|True|ジェネリックパラメーター *t*によって指定された <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> コレクション内の項目の型。既定では、 **Typeargument**は**Int32**に設定されています。 **Parallelforeach \<T >** アクティビティデザイナーで型 T を変更するには、プロパティグリッドの**typeargument**コンボボックスの値を変更します。|
|<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>|True|反復処理を行う項目のコレクション。 @No__t_0 を設定するには、 **[プロパティ]** ウィンドウの VB の式を入力してください ボックスまたは **[値]** ボックスに、 **ForEach \<T >** アクティビティデザイナーの **[値]** ボックスに [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 式を入力します。|
|<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>||各イテレーションの完了後に評価されます。 true であると評価する場合、スケジュールされた保留イテレーションはキャンセルされます。 このプロパティが設定されていない場合、スケジュールされたすべてのステートメントは、完了するまで実行されます。|

 既定では、ループ反復子には、item という名前が付けられます。 反復子変数の名前は、 **parallelforeach \<T >** アクティビティデザイナーの **[foreach]** ボックスで変更できます。 ループ反復子は、<xref:System.Activities.Statements.ParallelForEach%601> アクティビティの子の式で使用できます。

## <a name="see-also"></a>参照
 [シーケンス](../workflow-designer/sequence-activity-designer.md)の[並列](../workflow-designer/parallel-activity-designer.md)[制御フロー](../workflow-designer/control-flow-activity-designers.md)
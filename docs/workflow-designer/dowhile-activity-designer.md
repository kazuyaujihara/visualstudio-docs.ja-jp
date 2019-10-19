---
title: ワークフローデザイナー-DoWhile アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 85f8d6c442982fff47a679e8fc2ccc04ee515a9b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650526"
---
# <a name="dowhile-activity-designer"></a>DoWhile アクティビティ デザイナー

@No__t_0 アクティビティは、指定された条件が**false**と評価されるまで、<xref:System.Activities.Statements.DoWhile.Body%2A> に含まれるアクティビティを少なくとも1回実行します。 ループの本体に含まれるアクティビティを 0 回以上実行する必要がある場合は、代わりに、<xref:System.Activities.Statements.While> アクティビティを使用します。

## <a name="dowhile-properties-in-the-workflow-designer"></a>ワークフロー デザイナーでの DoWhile のプロパティ

次の表に、最も役に立つ <xref:System.Activities.Statements.DoWhile> アクティビティのプロパティを示し、デザイナーでそれらを使用する方法について説明します。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|条件が**true**のときに実行するアクティビティ。 @No__t_0 アクティビティを追加するには、"ここにアクティビティをドロップします" というヒントテキストが表示された**Dowhile**アクティビティデザイナーの **[Body]** ボックスに、[ツールボックス] からアクティビティをドロップします。|
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|True|ループの各繰り返しの後に評価する条件。 @No__t_0 を設定するには、 **Dowhile**アクティビティデザイナーまたはプロパティグリッドの **[条件]** ボックスに Visual Basic 式を入力します。|

## <a name="see-also"></a>関連項目

- [While](../workflow-designer/while-activity-designer.md)
- [制御フロー](../workflow-designer/control-flow-activity-designers.md)
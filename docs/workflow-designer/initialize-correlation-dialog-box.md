---
title: ワークフローデザイナー-[関連付けの初期化] ダイアログボックス
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InitializeCorrelation.UI
ms.assetid: 2a0a1cd3-7b9e-493e-9264-fcf85289ffcf
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d0b23f10184516ea4ffc3b00ac98e32ca8b387c1
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650192"
---
# <a name="initialize-correlation-dialog-box"></a>[関連付け初期化] ダイアログ ボックス

**[関連付けの初期化]** ダイアログボックスは、<xref:System.ServiceModel.Activities.InitializeCorrelation> アクティビティの <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> プロパティを編集するためにワークフローデザイナーで使用されます。 詳細については、「 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)」を参照してください。

次の表では、 **[関連付けの初期化]** ダイアログボックスのユーザーインターフェイス (UI) 要素について説明します。

|UI 要素|説明|
|-|-----------------|
|**相関関係**|初期化する関連付けの <xref:System.ServiceModel.Activities.CorrelationHandle>。|
|**初期化**|初期化するデータが格納されているキー/値ペア。 この値は、<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> プロパティに対応しています。 有効なキーと値のペアの例としては、OrderID という名前の変数と組み合わせた "OrderID" という名前のキーがあります。|

## <a name="to-launch-the-initialize-correlation-dialog-box"></a>[関連付け初期化] ダイアログ ボックスを開くには

**InitializeCorrelation**アクティビティデザイナーで **[表示]** をクリックするか、ワークフローデザイナーで <xref:System.ServiceModel.Activities.InitializeCorrelation> アクティビティを選択します。 次に、プロパティグリッドの [<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>] プロパティの横にある省略記号ボタンをクリックします。

## <a name="see-also"></a>関連項目

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
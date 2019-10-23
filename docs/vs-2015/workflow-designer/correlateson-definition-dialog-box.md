---
title: Correlateson の定義 ダイアログボックス |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e2a9a6f7ec6b8bf246ebfc03c166780b229e1aee
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656938"
---
# <a name="correlateson-definition-dialog-box"></a>[CorrelatesOn の定義] ダイアログ ボックス
**Correlateson** ] ダイアログボックスは、<xref:System.ServiceModel.Activities.Receive> アクティビティの <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> プロパティを編集するために [!INCLUDE[wfd1](../includes/wfd1-md.md)] で使用されます。 [Receive](../workflow-designer/receive-activity-designer.md)トピックを [!INCLUDE[crdefault](../includes/crdefault-md.md)] します。

 <xref:System.ServiceModel.Activities.Receive> アクティビティの間の相関関係によって、ワークフロー内でさまざまなサービス操作が相互に接続される方法が指定されます。

 次の表では、 **correlateson**  ダイアログボックスのユーザーインターフェイス (UI) 要素について説明します。

|UI 要素|説明|
|----------------|-----------------|
|**CorrelatesWith**|適切なワークフロー インスタンスにメッセージをルーティングするために使用される <xref:System.ServiceModel.Activities.CorrelationHandle>。|
|**XPath クエリ**|受信メッセージから相関関係データを抽出するためのクエリを含む、キーと値のペア。 これは、<xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> プロパティに対応します。 XPath クエリは、<xref:System.ServiceModel.MessageQuerySet> オブジェクトに含まれます。|

## <a name="to-launch-the-correlateson-dialog-box"></a>[CorrelatesOn] ダイアログ ボックスを起動するには
 **Receive**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所の [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 この操作により、Receive という既定の <xref:System.ServiceModel.Activities.Receive> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 **Receive**アクティビティデザイナーを選択し、 **correlateson Definition**  ダイアログボックスのプロパティグリッドで、 **correlateson**プロパティの (コレクション) テキストの横にある省略記号ボタンをクリックします。

## <a name="see-also"></a>関連項目
 [ [CorrelationInitializers の追加] ダイアログボックス <xref:System.ServiceModel.Activities.Receive> [](../workflow-designer/add-correlationinitializers-dialog-box.md) [関連付けの初期化](../workflow-designer/initialize-correlation-dialog-box.md)] ダイアログボックス
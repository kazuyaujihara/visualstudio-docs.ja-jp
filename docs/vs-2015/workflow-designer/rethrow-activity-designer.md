---
title: アクティビティデザイナーの再スロー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c65469242a60c64d6f31bfaea4fdbbf2d5251a34
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663369"
---
# <a name="rethrow-activity-designer"></a>Rethrow アクティビティ デザイナー
再**スロー**アクティビティデザイナーは、<xref:System.Activities.Statements.Rethrow> アクティビティを作成および構成するために使用されます。

## <a name="the-rethrow-activity"></a>Rethrow アクティビティ
 <xref:System.Activities.Statements.Rethrow> アクティビティでは、以前にスローされた例外をスローします。 このアクティビティは、<xref:System.Activities.Statements.Catch> アクティビティの <xref:System.Activities.Statements.TryCatch> ハンドラーでのみ使用できます。

### <a name="using-the-rethrow-activity-designer"></a>ReThrow アクティビティ デザイナーの使用
 再**スロー**アクティビティデザイナーは、 **[ツールボックス]** の **[エラー処理]** カテゴリにあります。これにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)] の左側にある **[ツールボックス]** タブをクリックします (または、 **[表示**] メニューまたは CTRL + ALT + X)

 再**スロー**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) にドロップして [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 これにより、Throw という既定の**DisplayName**を持つ <xref:System.Activities.Statements.Rethrow> アクティビティが作成されます。 @No__t_0 値は、再**スロー**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

### <a name="the-rethrow-properties"></a>Rethrow のプロパティ
 次の表に、<xref:System.Activities.Statements.Rethrow> のプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Rethrow> アクティビティの表示名を指定します (省略可能)。 既定値は Rethrow です。|

## <a name="see-also"></a>参照
 [コレクション](../workflow-designer/collection-activity-designers.md)[スロー](../workflow-designer/throw-activity-designer.md) [TryCatch](../workflow-designer/trycatch-activity-designer.md)
---
title: ワークフローデザイナー遅延アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5190807bba08f05e176acc15ac8daf42ac028c50
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650549"
---
# <a name="delay-activity-designer"></a>Delay アクティビティ デザイナー

**Delay**アクティビティデザイナーは、<xref:System.Activities.Statements.Delay> アクティビティを作成および構成するために使用されます。

## <a name="the-delay-activity"></a>Delay アクティビティ

<xref:System.Activities.Statements.Delay> アクティビティで、ワークフローの実行を、指定した時間だけ遅らせます。

### <a name="use-the-delay-activity-designer"></a>Delay アクティビティデザイナーの使用

**Delay**アクティビティデザイナーは、 **[ツールボックス]** の **[プリミティブ]** カテゴリにあります。このカテゴリにアクセスするには、ワークフローデザイナーの **[ツールボックス]** タブをクリックします。 または、 **[表示]** メニューの **[ツールボックス]** を選択するか、 **ctrl** +**Alt** +**X**キーを押します。

**Delay**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) にドロップしてワークフローデザイナー画面にドロップできます。 アクティビティデザイナーを削除すると、既定の <xref:System.Activities.Activity.DisplayName%2A> 遅延の <xref:System.Activities.Statements.Delay> アクティビティが作成されます。 @No__t_0 は、 **Delay**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

### <a name="the-delay-properties"></a>Delay プロパティ

次の表は、<xref:System.Activities.Statements.Delay> のプロパティと、デザイナーでのそれらの使用方法を示しています。 これらのプロパティは、プロパティグリッドで編集できます。また、一部のプロパティは、ワークフローデザイナー画面で編集できます。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Delay> アクティビティの表示名。 既定値は Delay です。 @No__t_0 値は厳密には必須ではありませんが、ベストプラクティスとして使用することをお勧めします。|
|<xref:System.Activities.Statements.Delay.Duration%2A>|True|ワークフローの実行を遅らせる時間の長さ。 このプロパティは、プロパティ グリッドで設定します。 時間の長さを指定するには、00:00:00 という形式のリテラル <xref:System.TimeSpan>、または Visual Basic の式を入力します。|

## <a name="see-also"></a>関連項目

- [Primitives](../workflow-designer/primitives-activity-designers.md)
- [Assign](../workflow-designer/assign-activity-designer.md)
- [Delay アクティビティ デザイナー](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)
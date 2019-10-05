---
title: ワークフローデザイナー-Persist アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Persist.UI
ms.assetid: be8648dd-3eb9-4a50-8ec1-57a8be804692
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7be70d18b1fc8ff12e2d1fb177b41775954334ed
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71254847"
---
# <a name="persist-activity-designer"></a>Persist アクティビティ デザイナー

**Persist**アクティビティデザイナーは、アクティビティを<xref:System.Activities.Statements.Persist>作成および構成するために使用されます。

## <a name="the-persist-activity"></a>Persist アクティビティ

<xref:System.Activities.Statements.Persist> アクティビティで、ワークフローをディスクに保存します (可能な場合)。 <xref:System.Activities.Statements.Persist> アクティビティは、<xref:System.Activities.Statements.TransactionScope> アクティビティ内などの非永続化ゾーンでは実行できません。 非永続化スコープで<xref:System.Activities.Statements.Persist>アクティビティを使用すると、実行時に例外がスローされます。

### <a name="using-the-persist-activity-designer"></a>Persist アクティビティ デザイナーの使用

**Persist**アクティビティデザイナーは、 **[ツールボックス**] の **[ランタイム]** カテゴリにあります。このカテゴリにアクセスするには、 **[ツール]** ボックス タブをクリックします (または、 **[表示]** メニューの **[ツールボックス]** を選択するか、CTRL + ALT + X キーを押します)。

**Persist**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意<xref:System.Activities.Statements.Sequence>の場所 (内など) にワークフローデザイナー画面にドロップできます。 これにより<xref:System.Activities.Statements.Persist> 、Persist という既定の**DisplayName**を持つアクティビティが作成されます。 は<xref:System.Activities.Activity.DisplayName%2A> 、 **Persist**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

### <a name="the-persist-properties"></a>Persist のプロパティ

次の表に、<xref:System.Activities.Statements.Persist> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティグリッドで編集することができ、一部のプロパティはワークフローデザイナー画面で編集できます。

|プロパティ名|必須|使用法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Persist> アクティビティの表示名。 既定値は Persist です。 表示名は必須ではありませんが、使用することをお勧めします。|

## <a name="see-also"></a>関連項目

- [ランタイム](../workflow-designer/runtime-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)
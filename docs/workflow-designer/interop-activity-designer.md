---
title: ワークフローデザイナー-相互運用アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Interop.UI
ms.assetid: 800a3403-ba86-41c4-8de1-c4fee9703eb1
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8047df3787c0871e369b6079e4f0cc80f6d93949
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650209"
---
# <a name="interop-activity-designer"></a>Interop アクティビティ デザイナー

**Interop**アクティビティデザイナーは、<xref:System.Activities.Statements.Interop> アクティビティを作成および構成するために使用されます。

## <a name="the-interop-activity"></a>Interop アクティビティ

<xref:System.Activities.Statements.Interop> アクティビティでは、ワークフロー内の <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName> から派生する型の実行を管理します。

### <a name="use-the-interop-activity-designer"></a>Interop アクティビティデザイナーの使用

**Interop**アクティビティデザイナーは、**ツールボックス**の **[移行]** カテゴリにあります。 **[ツールボックス] タブを**クリックしてアクセスします。または、 **[表示]** メニューの **[ツールボックス]** を選択するか、ctrl キーを押します。**Alt** +**X**+ ます。

@No__t_1 アクティビティを含む[移行](../workflow-designer/migration-activity-designers.md)カテゴリは、プロジェクトが 4 (完全) 以降を .NET Framework 対象としている場合にのみ、**ツールボックス**に表示されます。 必要に応じて、プロジェクトが対象とするフレームワークのバージョンを変更できます。

**Interop**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) にワークフローデザイナー画面にドロップできます。 **Interop**アクティビティデザイナーを削除すると、interop という既定の**DisplayName**を持つ <xref:System.Activities.Statements.Interop> アクティビティが作成されます。 @No__t_0 は、 **Interop**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

**Interop**アクティビティデザイナーまたはプロパティグリッドで、 **[ActivityType]** ボックス内のテキストをクリックして**参照**し、 **[.net 型の参照と選択]** ダイアログボックスを開きます。 ワークフロー3.0 またはワークフロー3.5 アクティビティの型のみが表示されます。 つまり、<xref:System.Workflow.ComponentModel.Activity> から派生した型のみが表示されます。 このボックスを使用して型を指定する方法の詳細については、「 [[.Net 型の参照と選択] ダイアログボックス](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box.md)」を参照してください。

### <a name="the-interop-properties"></a>Interop のプロパティ

次の表は、<xref:System.Activities.Statements.Interop> のプロパティと、デザイナーでのそれらの使用方法を示しています。 これらのプロパティは、プロパティグリッドまたはワークフローデザイナー画面で編集できます。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Interop> アクティビティの表示名。 既定値は**Interop**です。 表示名は必須ではありませんが、指定することをお勧めします。|
|<xref:System.Activities.Statements.Interop.ActivityType%2A>|True|<xref:System.Activities.Statements.Interop> アクティビティに含まれているアクティビティの型を指定します。 指定されたこの型は、<xref:System.Workflow.ComponentModel.Activity> から派生していることが必要です。|

## <a name="see-also"></a>関連項目

- [移行](../workflow-designer/migration-activity-designers.md)
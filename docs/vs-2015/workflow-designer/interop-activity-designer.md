---
title: Interop アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Interop.UI
ms.assetid: 800a3403-ba86-41c4-8de1-c4fee9703eb1
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 994d7776ff7c32f8dd309e667597550637ef2b5a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72659030"
---
# <a name="interop-activity-designer"></a>Interop アクティビティ デザイナー
**Interop**アクティビティデザイナーは、<xref:System.Activities.Statements.Interop> アクティビティを作成および構成するために使用されます。

## <a name="the-interop-activity"></a>Interop アクティビティ
 <xref:System.Activities.Statements.Interop> アクティビティでは、ワークフロー内の <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName> から派生する型の実行を管理します。

### <a name="using-the-interop-activity-designer"></a>Interop アクティビティ デザイナーの使用
 **Interop**アクティビティデザイナーは、[**ツールボックス]** の **[移行]** カテゴリにあります。このカテゴリにアクセスするには、 **[ツール]** ボックス タブをクリックします (または、 **[表示]** メニューの **[ツールボックス]** を選択するか、CTRL + ALT + X キーを押します)。

 @No__t_1 アクティビティを含む[移行](../workflow-designer/migration-activity-designers.md)カテゴリは、プロジェクトが完全 [!INCLUDE[netfx40_long](../includes/netfx40-long-md.md)] を対象としている場合にのみ、**ツールボックス**に表示されます。

 プロジェクトC#の場合は、**ソリューションエクスプローラー**でプロジェクトを右クリックし、 **[プロパティ]** を選択して、完全な [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] を使用するようにプロジェクトを再ターゲットできます。 **[アプリケーション]** タブで、**ターゲットフレームワーク**の **[NET Framework 4]** オプションを選択します。 この変更の確認を求めるメッセージが表示された **[ターゲットフレームワークの変更]** ダイアログボックスの **[はい]** をクリックします。

 VB プロジェクトの場合、[**ソリューションエクスプローラー**でプロジェクトを右クリックし、 **[プロパティ]** を選択すると、完全な [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] を使用するようにプロジェクトを再ターゲットできます。 **[コンパイル]** タブで、 **[詳細コンパイルオプション]** ボタンをクリックします。 [**ターゲットフレームワーク] ボックスの一覧**から **[.net framework 4]** を選択し、 **[OK]** をクリックします。 この変更の確認を求めるメッセージが表示された **[ターゲットフレームワークの変更]** ダイアログボックスの **[はい]** ボタンをクリックします。

 **Interop**アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) に [!INCLUDE[wfd2](../includes/wfd2-md.md)] 画面にドロップできます。 これにより、Interop という既定の**DisplayName**を持つ <xref:System.Activities.Statements.Interop> アクティビティが作成されます。 @No__t_0 は、 **Interop**アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。

 クリックして**参照...** **Interop**アクティビティデザイナーまたはプロパティグリッドの **[ActivityType]** ボックスにテキストを入力して、 **[.Net 型の参照と選択]** ダイアログボックスを表示します。 ワークフロー 3.0 またはワークフロー 3.5 のアクティビティの型のみ (つまり、<xref:System.Workflow.ComponentModel.Activity> から派生した型のみ) が表示されます。 このボックスを使用して型を指定 [!INCLUDE[crabout](../includes/crabout-md.md)] には、「 [.Net 型の参照と選択」ダイアログボックス](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box.md)のトピックを参照してください。

### <a name="the-interop-properties"></a>Interop のプロパティ
 次の表に、<xref:System.Activities.Statements.Interop> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドまたは[!INCLUDE[wfd2](../includes/wfd2-md.md)]画面で編集できます。

|プロパティ名|必須|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Interop> アクティビティの表示名。 既定値は Interop です。 表示名は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.Interop.ActivityType%2A>|True|<xref:System.Activities.Statements.Interop> アクティビティに含まれているアクティビティの型を指定します。 指定されたこの型は、<xref:System.Workflow.ComponentModel.Activity> から派生していることが必要です。|

## <a name="see-also"></a>関連項目
 [移行](../workflow-designer/migration-activity-designers.md)
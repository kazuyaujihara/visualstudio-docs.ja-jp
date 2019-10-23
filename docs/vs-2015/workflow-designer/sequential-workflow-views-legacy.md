---
title: シーケンシャルワークフロービュー (レガシ) |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- sequential workflow views
- sequential workflows, views
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
caps.latest.revision: 7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 8acc9bfcac476425ac6c6b967b1a3b3a34310d8a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663221"
---
# <a name="sequential-workflow-views-legacy"></a>シーケンシャル ワークフロー ビュー (レガシ)
[!INCLUDE[vs2010](../includes/vs2010-md.md)] は従来の [!INCLUDE[wfd1](../includes/wfd1-md.md)] を備えており、これを使用すると、[!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] または [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] を対象とすることができます。

 [!INCLUDE[wfd2](../includes/wfd2-md.md)] では、使い慣れた [!INCLUDE[wf](../includes/wf-md.md)] ユーザー インターフェイスを使用して [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] アプリケーションをグラフィカルに作成できます。 [!INCLUDE[wf](../includes/wf-md.md)] アプリケーションは、アクティビティと呼ばれるワークフロー プロセス ステップで構成されます。 ワークフローを作成するには、それぞれのアクティビティデザイナーを **[ツールボックス]** からデザインサーフェイスにドラッグして、デザイン画面でアクティビティを作成します。

 シーケンシャルワークフロー ( [(sequentialworkflowactivity)](http://go.microsoft.com/fwlink?LinkID=65040)) を作成すると、ワークフローの3つのビューを使用できるようになります。 これらのビューには、 **[ワークフロー]** メニューおよびデザインサーフェイスのコンテキストメニューからアクセスできます。

 各ビューの名前と説明の一覧を次の表に示します。

|メニュー/タブ オプション|説明|
|----------------------|-----------------|
|**SequentialWorkflow の表示**|デザインサーフェイスを右クリックし、コンテキストメニューの **[SequentialWorkflow の表示]** オプションを選択して **、シーケンシャルワークフロービューを**表示します。このビューには、シーケンシャルワークフローのアクティビティベースのグラフィック表現が表示されます。 または、 **[ワークフロー]** メニューの **[SequentialWorkflow の表示]** を選択します。|
|**キャンセルハンドラーの表示**|デザインサーフェイスを右クリックし、コンテキストメニューの **[キャンセルハンドラーの表示**] オプションを選択すると、**シーケンシャルワークフロー**ビューが表示されます。このビューには、ワークフローに関連付けられている[CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050)アクティビティが表示されます。 または、 **[ワークフロー]** メニューの **[キャンセルハンドラーの表示]** をクリックします。|
|**エラーハンドラーの表示**|デザインサーフェイスを右クリックし、コンテキストメニューの **[エラーハンドラーの表示]** オプションを選択すると、**エラー**ビューが表示されます。このビューには、ワークフローに関連付けられている[FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055)アクティビティが表示されます。 または、 **[ワークフロー]** メニューの **[エラーハンドラーの表示]** をクリックします。|

 類似ビューの詳細については、「[アクティビティビュー (レガシ)](../workflow-designer/activity-views-legacy.md)」を参照してください。

## <a name="see-also"></a>参照
 [アクティビティビュー (レガシ)](../workflow-designer/activity-views-legacy.md) [従来のワークフロープロジェクトの作成](../workflow-designer/creating-legacy-workflow-projects.md)[ワークフロー作成モード](http://go.microsoft.com/fwlink?LinkID=65014)
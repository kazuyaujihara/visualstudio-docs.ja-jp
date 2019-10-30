---
title: '方法: ワークフローにブレークポイントを設定する (レガシ) |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- breakpoints, setting in workflows
- debugging, setting breakpoints in workflows
- debugging workflows, setting breakpoints
- workflows, setting breakpoints
ms.assetid: 78e0be39-3e99-487c-bfef-19db0daf6f42
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 182f28a2b21ae3129ce0d34fae97280ba0a07218
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72603597"
---
# <a name="how-to-set-breakpoints-in-workflows-legacy"></a>方法: ワークフロー内にブレークポイントを設定する (レガシ)
このトピックでは、従来の [!INCLUDE[wf](../includes/wf-md.md)]を使用して作成された [!INCLUDE[wfd1](../includes/wfd1-md.md)] アプリケーションでブレークポイントを設定する方法について説明します。 [!INCLUDE[wfd2](../includes/wfd2-md.md)] アプリケーションが [!INCLUDE[wf2](../includes/wf2-md.md)] または [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] を対象とする必要がある場合は、従来の[!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)]を使用します。

 [!INCLUDE[wfd2](../includes/wfd2-md.md)] の従来の[!INCLUDE[vs2010](../includes/vs2010-md.md)]を使用して [!INCLUDE[wf2](../includes/wf2-md.md)] アプリケーションを作成した場合、Visual Studio と同様に、ブレークポイントを C# および Visual Basic コードで設定できます。 設定したそれぞれのブレークポイントで、ワークフローの実行が停止します。

 ブレークポイントには次の3つの状態があります。*保留中*、*バインド*済み、*エラー*。 ブレークポイントは設定時には「保留」になり、穴の空いた赤いアイコンで表示されます。 特定の種類のワークフローがランタイムによって読み込まれると、「バインド」になり、穴のない赤いアイコンで表示されます。 不適切な形式のブレークポイントを指定した場合 (たとえばアクティビティ名が無効など)、エラー ウィンドウが表示されます。 ブレークポイントはブレークポイント ウィンドウに追加されますが、小さな x 印が付きます。

 次のような方法で、ワークフロー デザイン サーフェイス上でアクティビティのブレークポイントを設定できます。

- アクティビティを右クリックし、**ブレークポイント**、ブレークポイントの挿入 の順に選択します。

- アクティビティを選択して、F9 キーを押します。

- **[デバッグ]** メニューの **[新しいブレークポイント]** をクリックします。

     また、このオプションを使用して、デバッグ中にデバッガがブレークポイントで停止したときに新しいブレークポイントを設定することもできます。

    > [!NOTE]
    > 呼び出されるワークフローに対してブレークポイントを設定することはできません。

### <a name="to-set-a-breakpoint-using-the-new-breakpoint-option-on-the-debug-menu"></a>[デバッグ] メニューの [ブレークポイントの作成] オプションを使ってブレークポイントを設定するには

1. **[デバッグ]** メニューの **[ブレークポイントの作成]** をクリックします。

2. **[関数で中断]** をクリックします。

     **[ブレークポイントの新規作成]** ダイアログボックスが表示されます。

3. **[関数]** テキストボックスで、次の構文を使用してアクティビティの名前を指定します。 `QualifiedActivityId[:[FullClassName][:InstanceId]]`。

    > [!NOTE]
    > 必要に応じて、 **[関数]** テキストボックスでアクティビティ名を使用する代わりに、ワークフローアクティビティの絶対パスを指定してブレークポイントを設定できます。 たとえば、 **workflowconsoleapplication1.workflow1**という名前のワークフローソリューションと、 **Delay1**というアクティビティを使用する**workflow1.xaml**という名前のソリューションのワークフローがあるとします。 アクティビティ名**Delay1**を使用するか、パスを**Delay1: Workflowconsoleapplication1.workflow1**または Delay1: workflowconsoleapplication1.workflow1 **: {workflow1.xaml 14886a6608e47 12bf98-99 ff15-6dddf}** として指定することができます。

4. [ **IntelliSense を使用**する] チェックボックスをオンにして、関数名を確認します。

     このチェック ボックスをオンにしない場合、ブレークポイント名は検証されません。

5. **[言語]** ボックスの一覧から **[ワークフロー]** を選択します。

6. **[OK]** をクリックします。

## <a name="see-also"></a>関連項目
 [Windows Workflow Foundation のための Visual Studio デバッガーを呼び出す](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)[従来のワークフローのデバッグ (レガシ)](../workflow-designer/debugging-legacy-workflows.md)
---
title: UWP のデバッグ時に中断/再開/バックグラウンドイベントをトリガーする
ms.custom: seodec18
ms.date: 01/16/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.error.background_task_activate_failure
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: d15a176fb378159407589af0b720d8310de8e29c
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72450406"
---
# <a name="how-to-trigger-suspend-resume-and-background-events-while-debugging-uwp-apps-in-visual-studio"></a>Visual Studio で UWP アプリのデバッグ中に中断イベント、再開イベント、およびバックグラウンドイベントをトリガーする方法

デバッグが行われていないときは、Windows の **プロセス継続時間管理** (PLM) によってアプリの実行状態 (ユーザー アクションに応じたアプリの開始、中断、再開、および終了) とデバイスの状態が管理されます。 デバッグが行われているとき、これらのアクティブ化イベントは Windows によって無効にされます。 このトピックでは、デバッガーでこれらのイベントを発生させる方法について説明します。

このトピックでは、 **バックグラウンド タスク**をデバッグする方法についても説明します。 バックグラウンドタスクを使用すると、アプリが実行されていない場合でも、バックグラウンドプロセスで特定の操作を実行できます。 デバッガーを使用してアプリをデバッグ モードに変更した後、UI の起動なしでバックグラウンド タスクを開始してデバッグできます。

プロセス継続時間管理とバックグラウンドタスクの詳細については、「[起動、再開、およびマルチタスキング](/windows/uwp/launch-resume/index)」を参照してください。

## <a name="BKMK_Trigger_Process_Lifecycle_Management_events"></a> プロセス継続時間管理イベントを発生させる
 Windows では、ユーザーがアプリから離れるか、Windows が低電力状態に入ったときに、アプリを中断できます。 `Suspending` イベントに応答して、関連するアプリとユーザー データを永続ストレージに保存し、リソースを解放できます。 **中断** 状態から再開されたアプリは **実行** 状態に入り、中断状態に入った時点の状態から実行を続行します。 `Resuming` イベントに応答してアプリの状態を復元するか更新し、リソースを再要求できます。

 Windows はできる限り多くの中断されたアプリをメモリに保持しようとしますが、十分なリソースが存在しない場合はアプリを終了できます。 ユーザーもアプリを明示的に閉じることができます。 ユーザーがアプリを閉じたことを示す特別なイベントはありません。

 Visual Studio デバッガーでは、アプリを手動で中断、再開、および終了して、プロセスのライフサイクル イベントをデバッグできます。 プロセスのライフサイクル イベントをデバッグするには:

1. デバッグするイベントのハンドラーにブレークポイントを設定します。

2. **F5** キーを押してデバッグを開始します。

3. **[デバッグの場所]** ツール バーで、トリガーするイベントを選択します。

     ![中断タスク、再開タスク、終了タスク、およびバックグラウンド タスク](../debugger/media/dbg_suspendresumebackground.png)

     **Suspend と terminate**は、アプリを閉じ、デバッグセッションを終了します。

## <a name="BKMK_Trigger_background_tasks"></a> バックグラウンド タスクをトリガーする
 すべてのアプリは、アプリが実行されていない場合でも特定のシステム イベントに応答するためのバックグラウンド タスクを登録できます。 バックグラウンド タスクは、UI を直接更新するコードは実行できません。代わりに、タイルの更新、バッジの更新、およびトースト通知を使用して、ユーザーに情報を表示します。 詳細については、「[バックグラウンドタスクを使用したアプリのサポート](https://msdn.microsoft.com/library/4c7bb148-eb1f-4640-865e-41f627a46e8e)」を参照してください。

 アプリのバックグラウンド タスクを開始するイベントをデバッガーからトリガーできます。

> [!NOTE]
> デバッガーは、データを含まないイベント (デバイスの状態の変更を示すイベントなど) だけをトリガーできます。 ユーザー入力やその他のデータを必要とするバックグラウンド タスクは手動でトリガーする必要があります。

 バックグラウンド タスク イベントをトリガーするための最も現実的な方法は、アプリが実行されていない時点です。 ただし、標準デバッグ セッション中のイベントのトリガーもサポートされています。

### <a name="BKMK_Trigger_a_background_task_event_from_a_standard_debug_session"></a> 標準デバッグ セッションからバックグラウンド タスク イベントをトリガーする

1. デバッグするバックグラウンド タスク コードの中にブレークポイントを設定します。

2. **F5** キーを押してデバッグを開始します。

3. **[デバッグの場所]** ツール バーのイベントの一覧から、開始するバックグラウンド タスクを選択します。

     ![中断タスク、再開タスク、終了タスク、およびバックグラウンド タスク](../debugger/media/dbg_suspendresumebackground.png)

### <a name="BKMK_Trigger_a_background_task_when_the_app_is_not_running"></a> アプリが実行されていないときにバックグラウンド タスクをトリガーする

1. デバッグするバックグラウンド タスク コードの中にブレークポイントを設定します。

2. スタートアップ プロジェクトのデバッグ プロパティ ページを開きます。 ソリューション エクスプローラーでプロジェクトを選択します。 **[デバッグ]** メニューの **[プロパティ]** をクリックします。

     プロジェクトC++の場合は、 **[構成プロパティ]** を展開し、 **[デバッグ]** をクリックします。

3. 次のいずれかの操作を行います。

    - Visual C# プロジェクトと Visual Basic プロジェクトの場合は、 **[起動しないが、開始時にコードをデバッグ]** をクリックします。

         ![C&#35;&#47;VB デバッグ起動アプリケーションプロパティ](../debugger/media/dbg_csvb_dontlaunchapp.png "DBG_CsVb_DontLaunchApp")

    - プロジェクトC++の場合は、 **[アプリケーションの起動]** ボックスの一覧の **[いいえ]** をクリックします。

         ![&#43;&#43;C&#47;VB アプリケーションデバッグプロパティの起動](../debugger/media/dbg_cppjs_dontlaunchapp.png "DBG_CppJs_DontLaunchApp")

4. **F5** キーを押して、アプリをデバッグ モードにします。 デバッグ モードであることを示すために、 **[デバッグの場所]** ツール バーの **[プロセス]** の一覧にアプリのパッケージ名が表示されます。

     ![バックグラウンドタスクのプロセス一覧](../debugger/media/dbg_backgroundtask_processlist.png "DBG_BackgroundTask_ProcessList")

5. **[デバッグの場所]** ツール バーのイベントの一覧から、開始するバックグラウンド タスクを選択します。

     ![中断、再開、終了、およびバックグラウンドタスク](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")

## <a name="BKMK_Trigger_Process_Lifetime_Management_events_and_background_tasks_from_an_installed_app"></a> インストール済みのアプリからプロセス継続時間管理イベントとバックグラウンド タスクをトリガーする
 **[インストールされているアプリケーションパッケージのデバッグ]** ダイアログボックスを使用すると、デバッガーに既にインストールされているアプリを読み込むことができます。 たとえば、Microsoft Store からインストールされたアプリをデバッグする場合や、アプリのソースファイルがあるものの、アプリの Visual Studio プロジェクトを使用しない場合にアプリをデバッグすることができます。 **[インストールされているアプリケーションパッケージのデバッグ]** ダイアログボックスを使用すると、Visual Studio コンピューターまたはリモートデバイスでデバッグモードでアプリを起動したり、デバッグモードで実行するようにアプリを設定したりすることができます。 詳細については、次を参照してください。 [インストールされているアプリ パッケージをデバッグ](../debugger/debug-installed-app-package.md)します。

 アプリをデバッガーに読み込んだら、前の各手順を使用できます。

## <a name="BKMK_Diagnosing_background_task_activation_errors"></a> バックグラウンド タスクのアクティブ化エラーの診断
 バックグラウンドインフラストラクチャ用の Windows イベントビューアーの診断ログには、バックグラウンドタスクエラーの診断とトラブルシューティングに使用できる詳細情報が含まれています。 このログを表示するには:

1. イベント ビューアー アプリケーションを開きます。

2. **操作** ウィンドウで、 **[表示]** をクリックし、 **[分析およびデバッグ ログの表示]** がオンになっていることを確認します。

3. **イベントビューアー (ローカル)** ツリーで、ノード **アプリケーションとサービスログ**  > **Microsoft**  > **Windows**  > **backgroundタスクインフラストラクチャ** の順に展開します。

4. **診断** ログを選択します。

## <a name="see-also"></a>参照
- [Visual Studio での UWP アプリのテスト](../test/testing-store-apps-with-visual-studio.md)
- [Visual Studio でのアプリのデバッグ](/visualstudio/debugger/debugging-windows-store-and-windows-universal-apps)
- [アプリケーションのライフサイクル](/windows/uwp/launch-resume/app-lifecycle)
- [Launching, resuming, and multitasking](/windows/uwp/launch-resume/index)
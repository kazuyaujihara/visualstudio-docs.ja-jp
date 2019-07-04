---
title: スナップショットのデバッグに関するトラブルシューティング | Microsoft Docs
ms.custom: ''
ms.date: 04/24/2019
ms.topic: troubleshooting
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e3c66ba4a5031326ec288d3a5f2f3c4851d17ca6
ms.sourcegitcommit: 74c5360186731de07828764eb32ea1033a8c2275
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "67559745"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Visual Studio でのスナップショットのデバッグに関するトラブルシューティングと既知の問題

この記事で説明されている手順を実行しても問題が解決しない場合、上の問題を検索[開発者コミュニティ](https://developercommunity.visualstudio.com/spaces/8/index.html)を選択して、新しい問題を報告または**ヘルプ** > **フィードバックの送信**  > **問題を報告する**Visual Studio でします。

## <a name="issue-attach-snapshot-debugger-encounters-an-http-status-code-error"></a>問題:HTTP 状態コード エラーが発生した「スナップショット デバッガーのアタッチ」

次のエラーが表示された場合、**出力**アタッチを試行中にウィンドウで、以下に示す既知の問題があります。 策の提案をお試しくださいし、問題が引き続き保持する場合は、上記のエイリアスにお問い合わせください。

`[TIMESTAMP] Error --- Unable to Start Snapshot Debugger - Attach Snapshot Debugger failed: System.Net.WebException: The remote server returned an error: (###) XXXXXX`

### <a name="401-unauthorized"></a>(401) 許可されていません

このエラーは、REST の呼び出しによって発行される Visual Studio Azure 使用するには、無効な資格情報を示します。 Azure Active Directory の簡単な OAuth モジュールを使用して既知のバグには、このエラーが発生します。

次の手順を実行します。

* Visual Studio のパーソナル化アカウントが Azure サブスクリプションとを接続しているリソースに権限を持っていることを確認します。 これを確認する簡単な方法がからダイアログ ボックスで、リソースが使用できるかどうかを確認するには**デバッグ** > **スナップショット デバッガーをアタッチしています.**  >  **Azure リソース** > **既存選択**、またはクラウド エクスプ ローラー。
* このエラーが引き続き保持する、この記事の冒頭で説明されているフィードバック チャネルのいずれかを使用します。

### <a name="403-forbidden"></a>(403) 許可されていません

このエラーは、アクセス許可が拒否されることを示します。 さまざまな問題の可能性があります。

次の手順を実行します。

* Visual Studio アカウントに、リソースのロールベースのアクセス制御 (RBAC) アクセス許可は必要な場合は、有効な Azure サブスクリプションがあることを確認します。 App Service では、確認する権限があるかどうか[クエリ](https://docs.microsoft.com/rest/api/appservice/appserviceplans/get)App Service プラン、アプリをホストします。
* クライアント コンピューターのタイムスタンプが正しく、最新の状態を確認します。 15 分以上の要求のタイムスタンプは、通常、オフのタイムスタンプを使用したサーバーでは、このエラーを生成します。
* このエラーが引き続き保持する、この記事の冒頭で説明されているフィードバック チャネルのいずれかを使用します。

### <a name="404-not-found"></a>(404) Not Found

このエラーは、web サイトは、そのサーバー上に見つかりませんでしたを示します。

次の手順を実行します。

* Web サイトを展開してアタッチする App Service リソースで実行されている、ことを確認します。
* サイトが https:// で使用できることを確認\<リソース\>azurewebsites.net。
* このエラーが引き続き保持する、この記事の冒頭で説明されているフィードバック チャネルのいずれかを使用します。

### <a name="406-not-acceptable"></a>(406) not Acceptable

このエラーは、サーバーが要求の Accept ヘッダーの種類に応答できることを示します。

次の手順を実行します。

* サイトが https:// で使用できることを確認\<リソース\>azurewebsites.net。
* サイトが新しいインスタンスにない移行されたことを確認します。 スナップショット デバッガーは、断続的にこのエラーを生成する特定のインスタンスへのルーティング要求を ARRAffinity の概念を使用します。
* このエラーが引き続き保持する、この記事の冒頭で説明されているフィードバック チャネルのいずれかを使用します。

### <a name="409-conflict"></a>(409) 競合

このエラーは、要求が現在のサーバーの状態と競合していることを示します。

これは、ユーザーが application Insights を有効にした app Service に対してスナップショット デバッガーをアタッチしようとしたときに発生する既知の問題です。 Application Insights では、この問題を引き起こしてより Visual Studio は、大文字小文字が異なると AppSettings を設定します。

::: moniker range=">= vs-2019"
これは、Visual Studio 2019 で解決されています。
::: moniker-end

次の手順を実行します。

::: moniker range="vs-2017"

* Azure portal で SnapshotDebugger (SNAPSHOTDEBUGGER_EXTENSION_VERSION) および InstrumentationEngine (INSTRUMENTATIONENGINE_EXTENSION_VERSION) AppSettings が大文字であることを確認します。 そうでない場合、設定の更新サイトの再起動を強制して、手動でします。
::: moniker-end
* このエラーが引き続き保持する、この記事の冒頭で説明されているフィードバック チャネルのいずれかを使用します。

### <a name="500-internal-server-error"></a>(500) の内部サーバー エラー

このエラーは、サイトが完全にダウンまたはサーバーが要求を処理できないことを示します。 スナップショット デバッガーのアプリケーションの実行でのみ機能します。 [Application Insights スナップショット デバッガー](https://docs.microsoft.com/azure/azure-monitor/app/snapshot-debugger)例外に関するスナップショットを作成を提供し、ニーズに最適なツールがあります。

### <a name="502-bad-gateway"></a>(502) 無効なゲートウェイ

このエラーは、サーバー側のネットワークの問題を示し、一時的な場合があります。

次の手順を実行します。

* スナップショット デバッガーをもう一度接続する前に数分待機していることをお試しください。
* このエラーが引き続き保持する、この記事の冒頭で説明されているフィードバック チャネルのいずれかを使用します。

## <a name="issue-snappoint-does-not-turn-on"></a>問題:スナップ ポイントを有効にしません

通常のスナップ アイコンではなく、![スナップポイントの警告アイコン](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "スナップポイントの警告アイコン")がスナップポイントに表示される場合、スナップポイントは有効ではありません。

![スナップポイントが有効にならない](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "スナップポイントが有効にならない")

次の手順を実行します。

1. 構築し、アプリのデプロイに使用されたソース コードの同じバージョンであることを確認します。 配置の正しいシンボルを読み込んでいることを確認します。 これを行うには、スナップショットのデバッグ中に **[モジュール]** ウィンドウを表示し、デバッグ対象のモジュール用に読み込まれた .pdb ファイルが [シンボル ファイル] 列に表示されることを確認します。 スナップショット デバッガーは、配置用のシンボルを自動的にダウンロードして使用しようとします。

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>問題:スナップショットを開くと、シンボルが読み込まれない

次のウィンドウが表示される場合、シンボルは読み込まれていません。

![シンボルが読み込まれない](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "シンボルが読み込まれない")

次の手順を実行します。

- このページの **[シンボルの設定の変更]** リンクをクリックします。 **[デバッグ] > [シンボル]** 設定で、シンボルのキャッシュ ディレクトリを追加します。 シンボルのパスを設定したら、スナップショットのデバッグを再開します。

   プロジェクトで使用できるシンボル、または .pdb ファイルは、App Service の配置と一致する必要があります。 ほとんどの配置 (Visual Studio、Azure Pipelines または Kudu を含む CI/CD などによる配置) は、シンボル ファイルを App Service に発行します。 シンボルのキャッシュ ディレクトリを設定すると、Visual Studio でそのシンボルを使用できるようになります。

   ![シンボルの設定](../debugger/media/snapshot-troubleshooting-symbol-settings.png "シンボルの設定")

- また、組織がシンボル サーバーを使用している場合、または別のパスにあるシンボルをドロップする場合は、シンボル設定を使用して配置の正しいシンボルを読み込みます。

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>問題:クラウド エクスプ ローラーで、「スナップショット デバッガーのアタッチ」オプションを表示できません。

次の手順を実行します。

- スナップショット デバッガー コンポーネントがインストールされていることを確認します。 Visual Studio インストーラーを開き、Azure ワークロードの**スナップショット デバッガー** コンポーネントをオンにします。
::: moniker range="< vs-2019"
- アプリがサポートされていることを確認します。 現在、Azure App Service にデプロイされている ASP.NET (4.6.1 以降) と ASP.NET Core (2.0 以降) のアプリケーションのみがサポートされています。
::: moniker-end
::: moniker range=">= vs-2019"
- アプリがサポートされていることを確認します。
  - Azure App Service - .NET Framework 4.6.1 以降で実行されている ASP.NET アプリケーション。
  - Azure App Service - Windows の .NET Core 2.0 以降で実行されている ASP.NET Core アプリケーション。
  - Azure Virtual Machines (および仮想マシン スケール セット) - .NET Framework 4.6.1 以降で実行されている ASP.NET アプリケーション。
  - Azure Virtual Machines (および仮想マシン スケール セット) - Windows 上の .NET Core 2.0 以降で実行されている ASP.NET Core アプリケーション。
  - Azure Kubernetes Service - Debian 9 上の .NET Core 2.2 以降で実行されている ASP.NET Core アプリケーション。
  - Azure Kubernetes Service - Alpine 3.8 上の .NET Core 2.2 以降で実行されている ASP.NET Core アプリケーション。
  - Azure Kubernetes Service - Ubuntu 18.04 上の .NET Core 2.2 以降で実行されている ASP.NET Core アプリケーション。
::: moniker-end

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>問題:診断ツールでのスナップショットの調整のみ表示します。

![調整されたスナップポイント](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "調整されたスナップポイント")

次の手順を実行します。

- スナップショットはほとんどメモリを占有しませんが、コミット チャージがかかります。 スナップショット デバッガーで、サーバーに大きなメモリ負荷がかかっていることが検出された場合は、スナップショットが取得されません。 既にキャプチャされたスナップショットを削除するには、スナップショット デバッガー セッションを停止して再試行します。

::: moniker range=">= vs-2019"
## <a name="issue-snapshot-debugging-with-multiple-versions-of-the-visual-studio-gives-me-errors"></a>問題:エラーには複数のバージョンの Visual Studio でスナップショットのデバッグ

Visual Studio 2019 では、Azure App Service でのスナップショット デバッガー サイト拡張機能の新しいバージョンが必要です。  このバージョンは、Visual Studio 2017 で使用されるスナップショット デバッガー サイト拡張機能の以前のバージョンで互換性がありません。  既に Visual Studio 2017 でのスナップショット デバッガーによってデバッグが完了する Azure App Service に Visual Studio 2019 のスナップショット デバッガーをアタッチしようとする場合、次のエラーが表示されます。

![互換性のないスナップショット デバッガー サイト拡張機能 Visual Studio 2019](../debugger/media/snapshot-troubleshooting-incompatible-vs2019.png "互換性のないスナップショット デバッガー サイト拡張機能 Visual Studio 2019")

逆に、Visual Studio 2017 を使用して以前の Visual Studio 2019 スナップショット デバッガーによってデバッグが完了する Azure App Service へのスナップショット デバッガーをアタッチすると、次のエラーが発生します。

![互換性のないスナップショット デバッガー サイト拡張機能 Visual Studio 2017](../debugger/media/snapshot-troubleshooting-incompatible-vs2017.png "互換性のないスナップショット デバッガー サイト拡張機能 Visual Studio 2017")

これを修正するには、Azure portal で次のアプリ設定を削除し、スナップショット デバッガーを再度アタッチします。

- INSTRUMENTATIONENGINE_EXTENSION_VERSION
- SNAPSHOTDEBUGGER_EXTENSION_VERSION
::: moniker-end

## <a name="issue-i-am-having-problems-snapshot-debugging-and-i-need-to-enable-more-logging"></a>問題:スナップショットのデバッグの問題があると、複数のログ記録を有効にする必要があります。

### <a name="enable-agent-logs"></a>エージェント ログを有効にする

エージェント ログを有効または無効にするには、Visual Studio を開き、 *[ツール] > [オプション] > [スナップショット デバッガー] > [エージェント ログを有効にする]* に移動します。 *[セッションの開始時に古いエージェント ログを削除する]* も有効な場合、Visual Studio のアタッチが成功するたびに以前のエージェント ログは削除される点に注意してください。

エージェント ログは次の場所にあります。

- App Service:
  - App Service の Kudu サイト (つまり yourappservice.**scm**.azurewebsites.net) にアクセスし、[デバッグ コンソール] に移動します。
  - エージェントのログは、次のディレクトリに格納されます。D:\home\LogFiles\SiteExtensions\DiagnosticsAgentLogs\
- VM/VMSS:
  - エージェントのログが次のように格納されている、VM にサインインします。C:\WindowsAzure\Logs\Plugins\Microsoft.Azure.Diagnostics.IaaSDiagnostics\<バージョン > \SnapshotDebuggerAgent_*.txt
- AKS
  - /tmp/diag/AgentLogs/* ディレクトリに移動します

### <a name="enable-profilerinstrumentation-logs"></a>プロファイラー/インストルメンテーション ログを有効にする

インストルメンテーション ログは次の場所にあります。

- App Service:
  - エラーのログ記録は D:\Home\LogFiles\eventlog.xml に自動的に送信される、イベントが付いて`<Provider Name="Instrumentation Engine" />`または"運用"ブレークポイント
- VM/VMSS:
  - VM にサインインし、イベント ビューアーを開きます。
  - 次のビューを開きます。*Windows ログ > アプリケーション*します。
  - *[Production Breakpoints]\(運用ブレークポイント\)* または *[インストルメンテーション エンジン]* を使用して、 *[イベント ソース]* で *[現在のログをフィルター]* を実行します。
- AKS
  - /tmp/diag/log.txt のインストルメンテーション エンジン ログ (DockerFile で MicrosoftInstrumentationEngine_FileLogPath を設定します)
  - /tmp/diag/shLog.txt の ProductionBreakpoint ログ

## <a name="known-issues"></a>既知の問題

- 同じ App Service に対する複数の Visual Studio クライアントを使用したスナップショットのデバッグは、現在サポートされていません。
- Roslyn IL の最適化は、ASP.NET Core プロジェクトでは完全にはサポートされていません。 一部の ASP.NET Core プロジェクトには、表示されない変数や、条件付きステートメントに使用できない変数があります。
- *$FUNCTION* や *$CALLER* などの特殊な変数は、ASP.NET Core プロジェクトの条件付きステートメントやログポイントで評価できません。
- スナップショットのデバッグは、[ローカル キャッシュ](/azure/app-service/app-service-local-cache)が有効な App Service では機能しません。
- スナップショット デバッグ API アプリは現在サポートされていません。

## <a name="site-extension-upgrade"></a>サイト拡張機能のアップグレード

スナップショットのデバッグと Application Insights は ICorProfiler に依存しています。ICorProfiler はサイト プロセスに読み込まれ、アップグレード中にファイル ロックの問題を引き起こします。 このプロセスで運用サイトにダウンタイムが発生しないようにすることをお勧めします。

- App Service 内に[デプロイ スロット](/azure/app-service/web-sites-staged-publishing)を作成し、サイトをスロットにデプロイします。
- Visual Studio の Cloud Explorer または Azure portal から、スロットを運用とスワップします。
- スロット サイトを停止します。 すべてのインスタンスからサイトの w3wp.exe プロセスを終了するため、この処理には数秒かかります。
- Kudu サイトまたは Azure portal からスロット サイト拡張機能をアップグレードします ( *[App Service] ブレード > [開発ツール] > [拡張機能] > [更新]* )。
- スロット サイトを起動します。 もう一度ウォームアップするために、このサイトにアクセスすることをお勧めします。
- スロットを運用とスワップします。

## <a name="see-also"></a>関連項目

- [Visual Studio でのデバッグ](../debugger/index.md)
- [スナップショット デバッガーを使用して、ライブ ASP.NET アプリをデバッグします。](../debugger/debug-live-azure-applications.md)
- [ライブ ASP.NET Azure 仮想 Machines\Virtual マシン スケール セットのスナップショット デバッガーを使用したデバッグします。](../debugger/debug-live-azure-virtual-machines.md)
- [スナップショット デバッガーを使用して、ライブの ASP.NET Azure Kubernetes デバッグします。](../debugger/debug-live-azure-kubernetes.md)
- [スナップショットのデバッグに関する FAQ](../debugger/debug-live-azure-apps-faq.md)

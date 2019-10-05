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
ms.openlocfilehash: 27df4c097d829a4d28a77b9b1ad96eb389f4096c
ms.sourcegitcommit: dc12a7cb66124596089f01d3e939027ae562ede9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71962938"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Visual Studio でのスナップショットのデバッグに関するトラブルシューティングと既知の問題

この記事で説明されている手順に従っても問題が解決しない場合は、[開発者コミュニティ](https://developercommunity.visualstudio.com/spaces/8/index.html)で問題を検索するか、Visual Studio で [**ヘルプ**@no__t]-2 [フィードバック**の** **送信**]  >  を選択して新しい問題を報告してください。

## <a name="issue-attach-snapshot-debugger-encounters-an-http-status-code-error"></a>問題:"Attach スナップショットデバッガー" で HTTP 状態コードエラーが発生する

アタッチしようとしたときに **[出力]** ウィンドウに次のエラーが表示される場合は、以下に示す既知の問題が考えられます。 提案されたソリューションを試してください。問題が解決しない場合は、前述のエイリアスに問い合わせてください。

`[TIMESTAMP] Error --- Unable to Start Snapshot Debugger - Attach Snapshot Debugger failed: System.Net.WebException: The remote server returned an error: (###) XXXXXX`

### <a name="401-unauthorized"></a>(401) 権限がありません

このエラーは、Visual Studio によって Azure に発行された REST 呼び出しに無効な資格情報が使用されていることを示します。 Azure Active Directory 簡易 OAuth モジュールに関する既知のバグによって、このエラーが発生することがあります。

次の手順を実行します。

* Visual Studio の個人用設定アカウントに、アタッチ先の Azure サブスクリプションとリソースへのアクセス許可があることを確認します。 これを簡単に確認するには、ダイアログボックスで、リソースが**デバッグ** > **Attach スナップショットデバッガー...**  > **Azure リソース** >  既存の、または Cloud Explorer で**選択し**ます。
* このエラーが引き続き発生する場合は、この記事の冒頭で説明したフィードバックチャネルのいずれかを使用します。

### <a name="403-forbidden"></a>(403) 許可されていません

このエラーは、アクセス許可が拒否されたことを示します。 これは、さまざまな問題が原因で発生する可能性があります。

次の手順を実行します。

* Visual Studio アカウントに、リソースに必要なロールベースの Access Control (RBAC) アクセス許可を持つ有効な Azure サブスクリプションがあることを確認します。 AppService の場合は、アプリをホストしている App Service プランに対して[クエリ](https://docs.microsoft.com/rest/api/appservice/appserviceplans/get)を実行するためのアクセス許可があるかどうかを確認します。
* クライアントコンピューターのタイムスタンプが正しいことと、最新の状態であることを確認します。 タイムスタンプが要求タイムスタンプから15分以上経過しているサーバーは、通常、このエラーを生成します。
* このエラーが引き続き発生する場合は、この記事の冒頭で説明したフィードバックチャネルのいずれかを使用します。

### <a name="404-not-found"></a>(404) が見つかりません

このエラーは、web サイトがサーバー上に見つからなかったことを示します。

次の手順を実行します。

* 接続している App Service リソースに web サイトがデプロイされ、実行されていることを確認します。
* サイトが https://\<resource\>.azurewebsites.net で利用可能であることを確認します。
* カスタム web アプリケーションを正しく実行すると、 https://\<resource\>.azurewebsites.net でアクセスしたときに、状態コード404が返されないことを確認します。
* このエラーが引き続き発生する場合は、この記事の冒頭で説明したフィードバックチャネルのいずれかを使用します。

### <a name="406-not-acceptable"></a>(406) 許容できません

このエラーは、サーバーが要求の Accept ヘッダーに設定されている型に応答できないことを示します。

次の手順を実行します。

* サイトが https://\<resource\>.azurewebsites.net で利用可能であることを確認します。
* サイトが新しいインスタンスに移行されていないことを確認します。 スナップショットデバッガーでは、特定のインスタンスに要求をルーティングするために ARRAffinity の概念を使用します。これにより、このエラーが断続的に発生する可能性があります。
* このエラーが引き続き発生する場合は、この記事の冒頭で説明したフィードバックチャネルのいずれかを使用します。

### <a name="409-conflict"></a>(409) 競合

このエラーは、要求が現在のサーバーの状態と競合していることを示します。

これは、ユーザーが ApplicationInsights を有効にした AppService に対してスナップショットデバッガーをアタッチしようとしたときに発生する既知の問題です。 ApplicationInsights は、この問題の原因となっている、Visual Studio とは異なる文字種の AppSettings を設定します。

::: moniker range=">= vs-2019"
これは Visual Studio 2019 で解決しました。
::: moniker-end

次の手順を実行します。

::: moniker range="vs-2017"

* Azure portal で、SnapshotDebugger (SNAPSHOTDEBUGGER_EXTENSION_VERSION) と InstrumentationEngine (INSTRUMENTATIONENGINE_EXTENSION_VERSION) の AppSettings が大文字であることを確認します。 構成されていない場合は、手動で設定を更新して、サイトを強制的に再起動します。
::: moniker-end
* このエラーが引き続き発生する場合は、この記事の冒頭で説明したフィードバックチャネルのいずれかを使用します。

### <a name="500-internal-server-error"></a>(500) 内部サーバーエラー

このエラーは、サイトが完全にダウンしているか、サーバーが要求を処理できないことを示します。 スナップショットデバッガー実行中のアプリケーションでのみ機能します。 [Application Insights スナップショットデバッガー](https://docs.microsoft.com/azure/azure-monitor/app/snapshot-debugger)では、例外のスナップショットが提供され、ニーズに最適なツールになる場合があります。

### <a name="502-bad-gateway"></a>(502) 無効なゲートウェイ

このエラーは、サーバー側のネットワークの問題であり、一時的なものである可能性があることを示します。

次の手順を実行します。

* スナップショットデバッガーを再度アタッチする前に、数分間待機してください。
* このエラーが引き続き発生する場合は、この記事の冒頭で説明したフィードバックチャネルのいずれかを使用します。

## <a name="issue-snappoint-does-not-turn-on"></a>問題:スナップポイントが有効にしない

通常のスナップ アイコンではなく、![スナップポイントの警告アイコン](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "スナップポイントの警告アイコン")がスナップポイントに表示される場合、スナップポイントは有効ではありません。

![スナップポイントが有効にならない](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "スナップポイントが有効にならない")

次の手順を実行します。

1. アプリのビルドとデプロイに使用されたのと同じバージョンのソースコードがあることを確認します。 配置の正しいシンボルを読み込んでいることを確認します。 これを行うには、スナップショットのデバッグ中に **[モジュール]** ウィンドウを表示し、デバッグ対象のモジュール用に読み込まれた .pdb ファイルが [シンボル ファイル] 列に表示されることを確認します。 スナップショット デバッガーは、配置用のシンボルを自動的にダウンロードして使用しようとします。

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>問題:スナップショットを開いたときにシンボルが読み込まれない

次のウィンドウが表示される場合、シンボルは読み込まれていません。

![シンボルが読み込まれない](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "シンボルが読み込まれない")

次の手順を実行します。

- このページの **[シンボルの設定の変更]** リンクをクリックします。 **[デバッグ] > [シンボル]** 設定で、シンボルのキャッシュ ディレクトリを追加します。 シンボルのパスを設定したら、スナップショットのデバッグを再開します。

   プロジェクトで使用できるシンボル、または .pdb ファイルは、App Service の配置と一致する必要があります。 ほとんどの配置 (Visual Studio、Azure Pipelines または Kudu を含む CI/CD などによる配置) は、シンボル ファイルを App Service に発行します。 シンボルのキャッシュ ディレクトリを設定すると、Visual Studio でそのシンボルを使用できるようになります。

   ![シンボルの設定](../debugger/media/snapshot-troubleshooting-symbol-settings.png "シンボルの設定")

- また、組織がシンボル サーバーを使用している場合、または別のパスにあるシンボルをドロップする場合は、シンボル設定を使用して配置の正しいシンボルを読み込みます。

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>問題:Cloud Explorer に "Attach スナップショットデバッガー" オプションが表示されない

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

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>問題:スロットルされたスナップショットのみが診断ツールに表示されます

![調整されたスナップポイント](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "調整されたスナップポイント")

次の手順を実行します。

- スナップショットはほとんどメモリを占有しませんが、コミット チャージがかかります。 スナップショット デバッガーで、サーバーに大きなメモリ負荷がかかっていることが検出された場合は、スナップショットが取得されません。 既にキャプチャされたスナップショットを削除するには、スナップショット デバッガー セッションを停止して再試行します。

::: moniker range=">= vs-2019"
## <a name="issue-snapshot-debugging-with-multiple-versions-of-the-visual-studio-gives-me-errors"></a>問題:複数バージョンの Visual Studio を使用したスナップショットデバッグでエラーが発生する

Visual Studio 2019 では、Azure App Service のスナップショットデバッガーサイト拡張機能の新しいバージョンが必要です。  このバージョンは、Visual Studio 2017 で使用される古いバージョンのスナップショットデバッガーサイト拡張機能と互換性がありません。  Visual studio 2019 のスナップショットデバッガーを Visual Studio 2017 のスナップショットデバッガーによって既にデバッグされている Azure App Service にアタッチしようとすると、次のエラーが表示されます。

![互換性のないスナップショットデバッガーサイト拡張機能 Visual studio 2019](../debugger/media/snapshot-troubleshooting-incompatible-vs2019.png "スナップショットデバッガーサイト拡張機能に互換性がありません visual studio 2019")

逆に、visual Studio 2017 を使用して、Visual Studio 2019 のスナップショットデバッガーによって以前にデバッグされていた Azure App Service にスナップショットデバッガーをアタッチすると、次のエラーが表示されます。

![互換性のないスナップショットデバッガーサイト拡張機能 Visual studio 2017](../debugger/media/snapshot-troubleshooting-incompatible-vs2017.png "スナップショットデバッガーサイト拡張機能に互換性がありません visual studio 2017")

これを修正するには、Azure portal で次のアプリ設定を削除し、スナップショット デバッガーを再度アタッチします。

- INSTRUMENTATIONENGINE_EXTENSION_VERSION
- SNAPSHOTDEBUGGER_EXTENSION_VERSION
::: moniker-end

## <a name="issue-i-am-having-problems-snapshot-debugging-and-i-need-to-enable-more-logging"></a>問題:スナップショットのデバッグで問題が発生したため、より多くのログ記録を有効にする必要があります

### <a name="enable-agent-logs"></a>エージェント ログを有効にする

エージェント ログを有効または無効にするには、Visual Studio を開き、 *[ツール] > [オプション] > [スナップショット デバッガー] > [エージェント ログを有効にする]* に移動します。 *[セッションの開始時に古いエージェント ログを削除する]* も有効な場合、Visual Studio のアタッチが成功するたびに以前のエージェント ログは削除される点に注意してください。

エージェント ログは次の場所にあります。

- App Service:
  - App Service の Kudu サイト (つまり yourappservice.**scm**.azurewebsites.net) にアクセスし、[デバッグ コンソール] に移動します。
  - エージェントのログは、次のディレクトリに格納されます。D:\home\LogFiles\SiteExtensions\DiagnosticsAgentLogs\
- VM/VMSS:
  - VM にサインインすると、エージェントのログは次のように格納されます。C:\WindowsAzure\Logs\Plugins\Microsoft.Azure.Diagnostics.IaaSDiagnostics @ no__t-0Version > \ snapshotデバッガ agent_ * .txt
- AKS
  - /tmp/diag/AgentLogs/* ディレクトリに移動します

### <a name="enable-profilerinstrumentation-logs"></a>プロファイラー/インストルメンテーション ログを有効にする

インストルメンテーション ログは次の場所にあります。

- App Service:
  - エラーログは D:\Home\LogFiles\eventlog.xml に自動的に送信され、イベントは `<Provider Name="Instrumentation Engine" />` または "運用ブレークポイント" でマークされます。
- VM/VMSS:
  - VM にサインインし、イベント ビューアーを開きます。
  - 次のビューを開きます。*Windows は > アプリケーションをログに記録*します。
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

- [Visual Studio でのデバッグ](../debugger/index.yml)
- [スナップショットデバッガーを使用したライブ ASP.NET アプリのデバッグ](../debugger/debug-live-azure-applications.md)
- [スナップショットデバッガーを使用したライブ ASP.NET Azure 仮想マシンの仮想マシンスケールセットのデバッグ](../debugger/debug-live-azure-virtual-machines.md)
- [スナップショットデバッガーを使用して live ASP.NET Azure Kubernetes をデバッグする](../debugger/debug-live-azure-kubernetes.md)
- [スナップショットのデバッグに関する FAQ](../debugger/debug-live-azure-apps-faq.md)

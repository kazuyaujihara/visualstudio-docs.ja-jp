---
title: スナップショットのデバッグに関するトラブルシューティング | Microsoft Docs
ms.custom: seodec18
ms.date: 11/07/2018
ms.topic: troubleshooting
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b7916cbd3a7faa633baf53a18686779dc2b386c
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58857763"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Visual Studio でのスナップショットのデバッグに関するトラブルシューティングと既知の問題

この記事に記載されている手順を実行しても問題が解決しない場合は、snaphelp@microsoft.com にお問い合わせください。

## <a name="issue-snappoint-does-not-turn-on"></a>問題:スナップ ポイントを有効にしません

通常のスナップ アイコンではなく、![スナップポイントの警告アイコン](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "スナップポイントの警告アイコン")がスナップポイントに表示される場合、スナップポイントは有効ではありません。

![スナップポイントが有効にならない](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "スナップポイントが有効にならない")

次の手順を実行します。

1. app.isua1 のビルドと配置に使用したものと同じバージョンのソース コードがあることを確認します。 配置の正しいシンボルを読み込んでいることを確認します。 これを行うには、スナップショットのデバッグ中に **[モジュール]** ウィンドウを表示し、デバッグ対象のモジュール用に読み込まれた .pdb ファイルが [シンボル ファイル] 列に表示されることを確認します。 スナップショット デバッガーは、配置用のシンボルを自動的にダウンロードして使用しようとします。

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

## <a name="issue-snapshot-debugging-with-multiple-versions-of-the-visual-studio-gives-me-errors"></a>問題:エラーには複数のバージョンの Visual Studio でスナップショットのデバッグ

VS 2019 では、Azure App Service 上に新しいバージョンのスナップショット デバッガー サイト拡張機能が必要です。  このバージョンは、VS 2017 で使用されている古いバージョンのスナップショット デバッガー サイト拡張機能と互換性がありません。  VS 2019 のスナップショット デバッガーを、VS 2017 のスナップショット デバッガーによって以前にデバッグされた Azure App Service にアタッチしようとすると、次のエラーが発生します。

![VS 2019 の互換性のないスナップショット デバッガー サイト拡張機能](../debugger/media/snapshot-troubleshooting-incompatible-vs2019.png "VS 2019 の互換性のないスナップショット デバッガー サイト拡張機能")

逆に、VS 2019 のスナップショット デバッガーによって以前にデバッグされた Azure App Service に、VS 2017 を使用してスナップショット デバッガーをアタッチすると、次のエラーが発生します。

![VS 2017 の互換性のないスナップショット デバッガー サイト拡張機能](../debugger/media/snapshot-troubleshooting-incompatible-vs2017.png "VS 2017 の互換性のないスナップショット デバッガー サイト拡張機能")

これを修正するには、Azure portal で次のアプリ設定を削除し、スナップショット デバッガーを再度アタッチします。

- INSTRUMENTATIONENGINE_EXTENSION_VERSION
- SNAPSHOTDEBUGGER_EXTENSION_VERSION

## <a name="issue-i-am-having-problems-snapshot-debugging-and-i-need-to-enable-more-logging"></a>問題:スナップショットのデバッグの問題があると、複数のログ記録を有効にする必要があります。

### <a name="enable-agent-logs"></a>エージェント ログを有効にする

エージェント ログを有効または無効にするには、Visual Studio を開き、*[ツール] > [オプション] > [スナップショット デバッガー] > [エージェント ログを有効にする]* に移動します。 *[セッションの開始時に古いエージェント ログを削除する]* も有効な場合、Visual Studio のアタッチが成功するたびに以前のエージェント ログは削除される点に注意してください。

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
  - エラー ログは自動的に D:\Home\LogFiles\eventlog.xml に送信され、イベントには <<Provider Name="Instrumentation Engine" //>> または "Production Breakpoints" とマークされます
- VM/VMSS:
  - VM にサインインし、イベント ビューアーを開きます。
  - 次のビューを開きます。*Windows ログ > アプリケーション*します。
  - *[Production Breakpoints]\(運用ブレークポイント\)* または *[インストルメンテーション エンジン]* を使用して、*[イベント ソース]* で *[現在のログをフィルター]* を実行します。
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
- Kudu サイトまたは Azure portal からスロット サイト拡張機能をアップグレードします (*[App Service] ブレード > [開発ツール] > [拡張機能] > [更新]*)。
- スロット サイトを起動します。 もう一度ウォームアップするために、このサイトにアクセスすることをお勧めします。
- スロットを運用とスワップします。

## <a name="see-also"></a>関連項目

- [Visual Studio でのデバッグ](../debugger/index.md)
- [スナップショット デバッガーを使用して、ライブ ASP.NET アプリをデバッグします。](../debugger/debug-live-azure-applications.md)
- [ライブ ASP.NET Azure 仮想 Machines\Virtual マシン スケール セットのスナップショット デバッガーを使用したデバッグします。](../debugger/debug-live-azure-virtual-machines.md)
- [スナップショット デバッガーを使用して、ライブの ASP.NET Azure Kubernetes デバッグします。](../debugger/debug-live-azure-kubernetes.md)
- [スナップショットのデバッグに関する FAQ](../debugger/debug-live-azure-apps-faq.md)
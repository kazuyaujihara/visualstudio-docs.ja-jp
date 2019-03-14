---
title: スナップショット デバッグのトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 9e2213c1e573efa1811d3b578c3d7bd92f1b77f2
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526417"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Visual Studio でスナップショットのデバッグのトラブルシューティングと既知の問題

この記事で説明されている手順を実行しても問題が解決しない場合にお問い合わせsnaphelp@microsoft.comします。

## <a name="issue-snappoint-does-not-turn-on"></a>問題: スナップ ポイントを有効にしません

警告アイコンを表示する場合![スナップ ポイントの警告アイコン](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "スナップ ポイントの警告アイコン")正規のスナップ ポイントのアイコンの代わりに、スナップ ポイントを使用し、スナップ ポイントがオンになっていません。

![スナップ ポイントの電源が入らない](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "スナップ ポイントを有効にしません")

次の手順を実行します。

1. 構築し、app.isua1 のデプロイに使用されたソース コードの同じバージョンであることを確認します。 展開に適切なシンボルを読み込んでいることを確認します。 これを行うには、表示、**モジュール**ウィンドウを選択し、スナップショットのデバッグ中にシンボル ファイルの列が .pdb ファイルをデバッグしているモジュールのアンロードの表示を確認します。 スナップショット デバッガーは、自動的にダウンロードして、デプロイ用のシンボルの使用を試みます。

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>問題: スナップショットを開くときにシンボルが読み込まれない

次のウィンドウが表示、シンボルが読み込まれませんでした。

![シンボルが読み込まれない](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "シンボルが読み込まれない")

次の手順を実行します。

- をクリックして、**シンボルの設定を変更しています.** このページにリンクします。 **デバッグ > シンボル**の設定は、シンボルのキャッシュ ディレクトリを追加します。 スナップショットのデバッグ シンボルのパスが設定された後に再起動します。

   記号、またはプロジェクトで使用できる .pdb ファイルは、App Service のデプロイと一致する必要があります。 ほとんどの配置 (Visual Studio]、[Azure パイプラインまたは Kudu を使用した CI/CD の配置など) に沿って、シンボル ファイルを App Service に発行します。 シンボルのキャッシュ ディレクトリを設定すると、Visual Studio を使用して、これらのシンボルが有効になります。

   ![シンボルの設定](../debugger/media/snapshot-troubleshooting-symbol-settings.png "シンボルの設定")

- または、組織では、シンボル サーバーを使用してまたは別のパスにシンボルを削除は、シンボルの設定を使用して、展開に適切なシンボルを読み込みます。

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>問題: クラウド エクスプ ローラーで「スナップショット デバッガーのアタッチ」オプションが表示できません。

次の手順を実行します。

- スナップショット デバッガーのコンポーネントがインストールされていることを確認します。 Visual Studio インストーラーを開き、確認、**スナップショット デバッガー** Azure ワークロードにコンポーネント。
::: moniker range="< vs-2019"
- アプリがサポートされていることを確認します。 現時点では、ASP.NET だけ (4.6.1+) し、Azure App Services にデプロイされた ASP.NET Core (2.0 以降) のアプリがサポートされます。
::: moniker-end
::: moniker range=">= vs-2019"
- アプリがサポートされていることを確認します。
  - Azure App Services の .NET Framework 4.6.1 で実行される ASP.NET アプリケーションまたはそれ以降。
  - Azure アプリ サービス - ASP.NET Core アプリケーションの .NET Core 2.0 または後で Windows を実行します。
  - .NET Framework 4.6.1 で実行されている azure の仮想マシン (と VMSS) では、ASP.NET アプリケーションまたはそれ以降。
  - Azure 仮想マシン (VMSS) - ASP.NET Core アプリケーションで .NET Core 2.0 または Windows の後で実行されています。
  - Azure Kubernetes サービス - .NET Core 2.2 または Debian 9 の後で実行されている ASP.NET Core アプリケーション。
  - Azure Kubernetes サービス - .NET Core 2.2 または後で Alpine 3.8 で実行されている ASP.NET Core アプリケーション。
  - Azure Kubernetes サービス - .NET Core 2.2 または後で Ubuntu 18.04 で実行されている ASP.NET Core アプリケーション。
::: moniker-end

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>問題: しか表示診断ツールでのスナップショットの調整

![調整されるスナップ ポイント](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "スナップ ポイントのスロットル")

次の手順を実行します。

- スナップショットは少量のメモリを占有しますが、コミット チャージを持っています。 スナップショット デバッガー検出されると、サーバーが負荷の高いメモリ負荷の下では、スナップショットになりません。 スナップショット デバッガー セッションを停止してから再試行して、既にキャプチャされているスナップショットを削除できます。

## <a name="known-issues"></a>既知の問題

- 同じ App Service に対して複数の Visual Studio クライアントでスナップショットのデバッグは現在サポートされていません。
- Roslyn の IL の最適化は ASP.NET Core プロジェクトで完全にサポートされていません。 いくつかの ASP.NET Core プロジェクトでは、いくつかの変数を参照してください。 または、条件付きステートメントでいくつかの変数を使用すること可能性がありますできません。
- 特別な変数など *$FUNCTION*または *$CALLER*、条件付きステートメントまたはログポイント ASP.NET Core プロジェクトで評価されることはできません。
- スナップショットのデバッグはアプリのサービスでは動作しません[ローカル キャッシュ](/azure/app-service/app-service-local-cache)オンにします。
- API アプリのデバッグ スナップショットは現在サポートされていません。

## <a name="site-extension-upgrade"></a>サイト拡張機能のアップグレード

スナップショットのデバッグと Application Insights は、サイトのプロセスに読み込まれ、アップグレード中にファイルのロックの問題が発生するの ICorProfiler に依存します。 運用サイトにダウンタイムがないことを確認するには、このプロセスをお勧めします。

- 作成、[デプロイ スロット](/azure/app-service/web-sites-staged-publishing)App Service 内およびサイト スロットをデプロイします。
- Visual Studio で Cloud Explorer から、または Azure portal から、運用スロットをスワップします。
- スロットのサイトを停止します。 すべてのインスタンスからサイト w3wp.exe プロセスを強制終了には数秒かかります。
- Kudu サイトまたは Azure portal からのスロットのサイト拡張機能のアップグレード (*アプリ サービス ブレード > 開発ツール > 拡張機能 > 更新*)。
- スロットのサイトを開始します。 もう一度ウォーム アップするサイトにアクセスすることをお勧めします。
- 運用スロットをスワップします。

## <a name="see-also"></a>関連項目

- [Visual Studio でのデバッグ](../debugger/index.md)
- [スナップショット デバッガーを使用して、ライブ ASP.NET アプリをデバッグします。](../debugger/debug-live-azure-applications.md)
- [ライブ ASP.NET Azure 仮想 Machines\Virtual マシン スケール セットのスナップショット デバッガーを使用したデバッグします。](../debugger/debug-live-azure-virtual-machines.md)
- [スナップショット デバッガーを使用して、ライブの ASP.NET Azure Kubernetes デバッグします。](../debugger/debug-live-azure-kubernetes.md)
- [スナップショットのデバッグに関する FAQ](../debugger/debug-live-azure-apps-faq.md)
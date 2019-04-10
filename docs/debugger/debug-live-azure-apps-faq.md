---
title: スナップショットのデバッグに関する FAQ | Microsoft Docs
ms.date: 11/07/2017
ms.topic: reference
helpviewer_keywords:
- debugger
ms.assetid: 944f1eb0-a74b-4d28-ae2b-a370cd869add
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7ea593ad5f88ba29f6b1c0d7c64a129b8f71c7f5
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58857075"
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>Visual Studio でのスナップショットのデバッグについてよく寄せられる質問

スナップショット デバッガーを使用してライブ Azure アプリケーションをデバッグするときに考えられる質問の一覧を以下に示します。

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>スナップショットの取得にはどのようなパフォーマンス コストがかかりますか?

スナップショット デバッガーがアプリのスナップショットをキャプチャすると、アプリのプロセスはフォークされ、フォークされたコピーは中断されます。 スナップショットをデバッグする場合、デバッグ対象はプロセスのフォークされたコピーです。 このプロセスにかかる時間はわずか 10 から 20 ミリ秒ですが、アプリのヒープ全体はコピーされません。 代わりに、ページ テーブルのみがコピーされ、書き込み時にコピーするページが設定されます。 ヒープ上のアプリのオブジェクトの一部が変更された場合は、それぞれのページがコピーされます。 各スナップショットのメモリ内コストが小さい理由はこのためです (ほとんどのアプリケーションでは数百キロバイト程度)。

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>スケールアウトされた Azure App Service (アプリの複数のインスタンス) があるとどうなりますか?

アプリのインスタンスが複数ある場合、スナップポイントはすべてのインスタンスに適用されます。 指定した条件で最初にヒットしたスナップポイントでのみ、スナップショットが作成されます。 複数のスナップポイントがある場合、後のスナップショットは最初のスナップショットを作成したものと同じインスタンスから取得されます。 出力ウィンドウに送信されたログポイントには、1 つのインスタンスのメッセージのみが表示されますが、アプリケーション ログに送信されたログポイントではすべてのインスタンスからメッセージが送信されます。

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>スナップショット デバッガーがシンボルを読み込む方法を教えてください。

スナップショット デバッガーを使用するには、ローカルのアプリケーションまたは Azure App Service にデプロイされているアプリケーションに一致するシンボルが必要です (埋め込みの PDB は現在サポートされていません)。スナップショット デバッガーでは、Azure App Service からシンボルが自動的にダウンロードされます。 Visual Studio 2017 バージョン 15.2 以降、Azure App Service にデプロイすると、アプリのシンボルもデプロイされます。

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>スナップショット デバッガーはアプリケーションのリリース ビルドに対して動作しますか?

はい。スナップショット デバッガーはリリース ビルドに対して動作するように設計されています。 スナップポイントが関数に配置されると、その関数はデバッグ バージョンに再コンパイルされ、デバッグ可能になります。 スナップショット デバッガーを停止すると、関数はリリース ビルドのバージョンに戻ります。

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>ログポイントが運用アプリケーションに副作用を及ぼす可能性はありますか?

いいえ。アプリに追加したログ メッセージは仮想的に評価されます。 アプリケーションに副作用を引き起こすことはありません。 ただし、ログポイントでは一部のネイティブ プロパティにアクセスできない場合があります。

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>サーバーに負荷がかかっていてもスナップショット デバッガーは機能しますか?

はい。スナップショットのデバッグは、サーバーに負荷がかかっていても機能します。 サーバーの空きメモリが少ない状況になると、スナップショット デバッガーが調整され、スナップショットがキャプチャされなくなります。

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>スナップショット デバッガーをアンインストールする方法を教えてください。

App Service からスナップショット デバッガー サイト拡張機能をアンインストールするには、次の手順を実行します。

1. Visual Studio の Cloud Explorer または Azure portal のいずれかを使用して App Service を無効にします。
1. App Service の Kudu サイト (つまり yourappservice.**scm**.azurewebsites.net) にアクセスし、**[サイト拡張機能]** に移動します。
1. スナップショット デバッガー サイト拡張機能の [X] をクリックして削除します。

#### <a name="why-are-ports-opened-during-a-snapshot-debugger-session"></a>スナップショット デバッガー セッション中にポートが開かれるのはなぜですか?

Azure で取得されたスナップショットをデバッグするために、スナップショット デバッガーでは一連のポートを開く必要があります。これらは、リモート デバッグに必要なポートと同じです。 [ポートの一覧については、こちらを参照してください](../debugger/remote-debugger-port-assignments.md)。

## <a name="see-also"></a>関連項目

- [Visual Studio でのデバッグ](../debugger/index.md)
- [スナップショット デバッガーを使用してライブ ASP.NET アプリをデバッグする](../debugger/debug-live-azure-applications.md)
- [スナップショット デバッガーを使用してライブ ASP.NET Azure Virtual Machines\Virtual Machine Scale Sets をデバッグする](../debugger/debug-live-azure-virtual-machines.md)
- [スナップショット デバッガーを使用してライブ ASP.NET Azure Kubernetes をデバッグする](../debugger/debug-live-azure-kubernetes.md)
- [スナップショットのデバッグに関するトラブルシューティングと既知の問題](../debugger/debug-live-azure-apps-troubleshooting.md)
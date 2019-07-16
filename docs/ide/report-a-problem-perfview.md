---
title: PerfView で ETL トレースを収集する
ms.date: 06/27/2019
ms.topic: conceptual
helpviewer_keywords:
- perfview
- ETL Trace
author: mikeblome
ms.author: mblome
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.description: Use perfview.exe to collect ETL traces for troubleshooting issues with Visual Studio
ms.openlocfilehash: baae89b7bf45a4848c571f75e37c6cc0d203d459
ms.sourcegitcommit: 6f7a740750b2cd17ea2275c3d046caebc9782917
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67518188"
---
# <a name="collect-an-etl-trace-with-perfview"></a>PerfView で ETL トレースを収集する

PerfView は、[Windows イベント トレーシング](/windows/desktop/ETW/event-tracing-portal)に基づいて ETL (イベント トレース ログ) ファイルを作成するツールです。これは Visual Studio に関する一部の問題をトラブルシューティングするのに役立ちます。 お客様が問題を報告したときに、製品チームから、PerfView を実行して追加情報を収集していただくようお願いする場合があります。

## <a name="install-perfview"></a>PerfView のインストール

[Microsoft ダウンロード センター](http://www.microsoft.com/download/details.aspx?id=28567)から PerfView をダウンロードします。

## <a name="run-perfview"></a>PerfView の実行

1. Windows エクスプローラーで **PerfView.exe** を右クリックし、管理者として **[管理者として実行]** を選択します
1. [収集] メニューで、 **[収集]** を選択します
1. **[Zip]** 、 **[結合]** 、 **[ThreadTime]** をチェックします。
1. **[Circular MB]\(循環 MB\)** を 1000 に増やします。
1. **[Current Dir]\(現在のディレクトリ\)** を変更し、指定したフォルダーに ETL トレースを保存します。2 回以上収集する場合は、[データ ファイル] も変更します。
1. データの記録を開始するには、 **[収集の開始]** ボタンを選択します。
1. データの記録を停止するには、 **[収集の停止]** ボタンを選択します。 PrefView.etl.zip ファイルが指定したディレクトリに保存されます。

PerfView を使って保存できるのは、そのバッファーに収まる最新のデータのみです。 そのため、Visual Studio がフリーズしたり、速度が低下したりしたら、できるだけ早く収集を停止するようにしてください。 問題が発生した後 30 秒以上収集を行わないようにしてください。

詳細については、[Channel9 のPerfView チュートリアル](http://channel9.msdn.com/Series/PerfView-Tutorial/PerfView-Tutorial-1-Collecting-data-with-the-Run-command)に関するページをご覧ください。

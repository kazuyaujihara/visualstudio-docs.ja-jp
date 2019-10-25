---
title: デバッガーサービスのメモリが不足しています |Microsoft Docs
ms.date: 07/10/2019
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.debug_no_memory
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger
author: isadorasophia
ms.author: isgarcia
manager: caslan
ms.workload:
- multiple
ms.openlocfilehash: 12215f9c740e68c4f2749a51b06c09a1385dae1a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72737838"
---
# <a name="debugger-services-running-out-of-memory"></a>デバッガー サービスのメモリが不足しています
デバッグサービスのメモリが不足しており、デバッグセッションが終了しました。

## <a name="to-investigate-this-error-on-windows"></a>Windows でこのエラーを調査するには
- **[診断ツール]** ウィンドウのプロセスメモリグラフを確認すると、対象アプリケーションのメモリの増加が大きくなっているかどうかを確認できます。 その場合は、**メモリ使用量**ツールを使用して根本的な問題を診断し、「[メモリ使用量の分析](../profiling/memory-usage.md)」を参照してください。

- ターゲットアプリケーションが大量のメモリを消費していると思わない場合は、**タスクマネージャー**ウィンドウを使用して、Visual Studio (devenv.exe)、ワーカープロセス (tlbimp.exe)、または VS Code (vsdbg) のメモリ使用量を確認し、これがであるかどうかを確認します。デバッガーの問題です。 メモリが不足しているプロセスが devenv.exe の場合は、実行されている Visual Studio 拡張機能の数を減らすことを検討してください。

## <a name="see-also"></a>関連項目
- [ブログ投稿: デバッグ中の CPU とメモリの分析](https://devblogs.microsoft.com/visualstudio/analyze-cpu-memory-while-debugging/)
- [メモリ管理について](/windows/win32/memory/about-memory-management)

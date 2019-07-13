---
title: デバッガーのメモリが不足サービス |Microsoft Docs
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
ms.openlocfilehash: 05664ffd056f69215e6fb00d6d49a59382a3692f
ms.sourcegitcommit: da4079f5b6ec884baf3108cbd0519d20cb64c70b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "67854019"
---
# <a name="debugger-services-running-out-of-memory"></a>デバッガーのメモリ不足実行されているサービス
サービスのデバッグは、メモリが不足し、デバッグ セッションの終了の原因とします。

## <a name="to-investigate-this-error-on-windows"></a>Windows では、このエラーを調査するには
- プロセスのメモリ グラフのチェックイン、**診断ツール**対象アプリケーションにメモリ内の急激な成長が発生しているかどうかに表示するウィンドウ。 場合は、使用、**メモリ使用量**ものを診断するためのツールは、基になる問題を参照してください[メモリ使用率の分析](../profiling/memory-usage.md)します。

- ターゲット アプリケーションが大量のメモリを消費していない場合は、使用、**タスク マネージャー**するメモリ使用量の Visual Studio (devenv.exe)、ワーカー プロセス (msvsmon.exe)、または VS Code (vsdbg.exe/vsdbg-ui.exe) のために確認するにはウィンドウデバッガーの問題を確認します。 Devenv.exe の場合は、メモリ不足しているプロセスを実行している Visual Studio 拡張機能の数を減らすことを検討してください。

## <a name="see-also"></a>関連項目
- [ブログの投稿:デバッグ中に CPU とメモリを分析します。](https://devblogs.microsoft.com/visualstudio/analyze-cpu-memory-while-debugging/)
- [メモリ管理について](/windows/win32/memory/about-memory-management)

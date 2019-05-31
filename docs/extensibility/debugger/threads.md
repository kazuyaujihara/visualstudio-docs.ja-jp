---
title: スレッド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e9759536e1b27018a3361bbb723b4cde0f88269e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66333655"
---
# <a name="threads"></a>スレッド
デバッガーのアーキテクチャで、*スレッド*:

- 計算の基本的な単位です。 スレッドには、その手順を次に、1 つのコード コンテキストから移動を単一の呼び出し履歴のコンテキスト内で順番に実行します。

- それ自体とで実行されているプログラムを識別できます。 スレッドは、という名前の中断、および再開できます。 スレッドはまた、関連付けられているスタック フレームを列挙し、いくつかの条件下では、別のスタック フレームに移動できます。 スタック フレームのコンテキストを指定するには、スレッドを返せるその関連付けられた論理スレッド存在する場合。 スレッドが中断カウントに表示されることがあるなどのプロパティ、**スレッド**IDE のウィンドウ。

- によって表される、 [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md)インターフェイス、通常、デバッグ エンジン (DE) またはプログラムを実行するための仮想マシンを作成します。

## <a name="see-also"></a>関連項目
- [プログラム](../../extensibility/debugger/programs.md)
- [スタック フレーム](../../extensibility/debugger/stack-frames.md)
- [デバッグ エンジン](../../extensibility/debugger/debug-engine.md)
- [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)
- [セッション デバッグ マネージャー](../../extensibility/debugger/session-debug-manager.md)
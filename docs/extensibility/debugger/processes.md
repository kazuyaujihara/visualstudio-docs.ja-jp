---
title: プロセス |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5c45fc70fe61c7221a8042d275dd44d69eb5d11e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351490"
---
# <a name="processes"></a>プロセス
デバッガーのアーキテクチャで、*プロセス*:

- プログラムの一連のコンテナーです。 Windows プロセス、スレッドのセットのコンテナーであると密接に似ています。

- 名前、識別子、または物理的な識別子で自身を識別できます。

- 実行中のすべてのプログラム (とそのスレッド) を列挙できます。

- 自体では、実行されているポートとそれを含んでいるマシンを記述できます。

- 1 つを作成したり、他のプログラムの作成、プログラムを終了またはプログラムを停止します。

- によって表される、 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)インターフェイスで、プロセスを起動するときに作成されます。 いずれかのセッション デバッグ マネージャー (SDM) プロセスの起動時または[LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)します。

  パッケージのデバッグは呼び出すことによって、プロセスにデバッグ エンジン (DE) をアタッチすることができます[アタッチ](../../extensibility/debugger/reference/idebugprocess2-attach.md)デが処理できるプロセスで実行されているすべての可能なプログラムにアタッチすることを意味します。 たとえば場合、DE、共通言語ランタイムは、プロセスにアタッチして、マネージ コードが実行されているプログラムのみにアタッチします。

## <a name="see-also"></a>関連項目
- [プログラム](../../extensibility/debugger/programs.md)
- [スレッド](../../extensibility/debugger/threads.md)
- [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)
- [パッケージをデバッグします。](../../extensibility/debugger/debug-package.md)
- [デバッグ エンジン](../../extensibility/debugger/debug-engine.md)
- [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)
- [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)
- [Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md)
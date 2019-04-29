---
title: プロセス |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1453aadebfaacb6ff4232f02eb22d4e69a94c840
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925287"
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
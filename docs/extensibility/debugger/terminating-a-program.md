---
title: プログラムの終了 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 729d37c36782cd1786124c94796f610931473f0c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62912750"
---
# <a name="terminating-a-program"></a>プログラムの終了
次のセクションでは、1 つのスレッドで 1 つのプログラムの終了について説明します。

## <a name="termination-process"></a>終了プロセス

1. DE 送信、 [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)有効な[IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md)します。

2. DE 送信、 [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)有効な[IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)します。

   IDE は、デザイン モードに入ります。 デバッグ エンジンまたはランタイム環境は[IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)ポートからプログラムを削除します。

## <a name="see-also"></a>関連項目
- [デバッガー イベントの呼び出し](../../extensibility/debugger/calling-debugger-events.md)
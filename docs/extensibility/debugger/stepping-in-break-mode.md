---
title: 中断モードでのステップ実行 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eb7b7e847c116f3aab38a12ec9801988bb8b3fc1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62912845"
---
# <a name="stepping-in-break-mode"></a>中断モードでのステップ実行
次のセクションでは、デバッガーが中断モードとコードをステップ実行する必要があるときに発生するプロセスについて説明します。

## <a name="stepping-process"></a>プロセスをステップ実行

1. 呼び出す[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)で[STEPKIND](../../extensibility/debugger/reference/stepkind.md)と[STEPUNIT](../../extensibility/debugger/reference/stepunit.md)ステップを実行する引数。

2. ステップが完了したら、送信、 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) stopping イベントとして。

## <a name="see-also"></a>関連項目
- [デバッガー イベントの呼び出し](../../extensibility/debugger/calling-debugger-events.md)
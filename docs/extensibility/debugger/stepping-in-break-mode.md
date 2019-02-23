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
ms.openlocfilehash: 66e7e227daa0dd58bf24ae946cce667992e09f90
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685028"
---
# <a name="stepping-in-break-mode"></a>中断モードでのステップ実行
次のセクションでは、デバッガーが中断モードとコードをステップ実行する必要があるときに発生するプロセスについて説明します。

## <a name="stepping-process"></a>プロセスをステップ実行

1.  呼び出す[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)で[STEPKIND](../../extensibility/debugger/reference/stepkind.md)と[STEPUNIT](../../extensibility/debugger/reference/stepunit.md)ステップを実行する引数。

2.  ステップが完了したら、送信、 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) stopping イベントとして。

## <a name="see-also"></a>関連項目
- [デバッガー イベントの呼び出し](../../extensibility/debugger/calling-debugger-events.md)
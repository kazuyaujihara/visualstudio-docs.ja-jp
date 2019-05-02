---
title: 中断モードでのステップ実行 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 482d7131692c1e22483c80f4b4bb22e07a6caf1a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62423362"
---
# <a name="stepping-in-break-mode"></a>中断モードへのステップイン
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

次に、デバッガーが中断モードとコードをステップ実行する必要があるときに発生するプロセスについて説明します。  
  
## <a name="stepping-process"></a>プロセスをステップ実行  
  
1. 呼び出す[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)で[STEPKIND](../../extensibility/debugger/reference/stepkind.md)と[STEPUNIT](../../extensibility/debugger/reference/stepunit.md)ステップを実行する引数。  
  
2. ステップが完了したら、送信、 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) stopping イベントとして。  
  
## <a name="see-also"></a>関連項目  
 [デバッガーのイベントの呼び出し](../../extensibility/debugger/calling-debugger-events.md)

---
title: ブレークポイントのヒット |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0ddf7fd92ac0b2f745f9e73170de22e9724dad76
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60074421"
---
# <a name="hitting-a-breakpoint"></a>ブレークポイントのヒット
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

次に示します (DE) デバッグ エンジンが実行されている、またはステップ実行中にブレークポイントをヒットしたときのプロセスを。  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>ブレークポイントをヒットのトラブルシューティング  
  
1. DE 送信、 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)インターフェイスとして、 **EVENT_SYNC_STOP**します。  
  
2. セッション デバッグ マネージャー (SDM) を呼び出す[IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md)ヒットしたブレークポイントを取得します。  
  
## <a name="see-also"></a>関連項目  
 [デバッガーのイベントの呼び出し](../../extensibility/debugger/calling-debugger-events.md)

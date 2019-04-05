---
title: ブレークポイントの削除 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9a70cfe5b728cc9af019752bd0c9c9d2f5105043
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973875"
---
# <a name="deleting-a-breakpoint"></a>ブレークポイントの削除
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

次に示します保留中のブレークポイントを削除するときのプロセスを。  
  
## <a name="deletion-process"></a>削除プロセス  
 セッション デバッグ マネージャー (SDM) を呼び出す、 [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)から保留中のブレークポイントとバインドされたすべてのブレークポイントを削除するメソッドにバインドされています。  
  
> [!NOTE]
>  呼び出して 1 つのバインドされたブレークポイントを削除することも[IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)します。  
  
## <a name="see-also"></a>関連項目  
 [デバッガーのイベントの呼び出し](../../extensibility/debugger/calling-debugger-events.md)

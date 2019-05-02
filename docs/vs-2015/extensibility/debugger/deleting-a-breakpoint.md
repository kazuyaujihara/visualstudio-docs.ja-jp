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
ms.openlocfilehash: 42cd353c216c21d14c4f6592da809c72acdba664
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63409406"
---
# <a name="deleting-a-breakpoint"></a>ブレークポイントの削除
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

次に示します保留中のブレークポイントを削除するときのプロセスを。  
  
## <a name="deletion-process"></a>削除プロセス  
 セッション デバッグ マネージャー (SDM) を呼び出す、 [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)から保留中のブレークポイントとバインドされたすべてのブレークポイントを削除するメソッドにバインドされています。  
  
> [!NOTE]
> 呼び出して 1 つのバインドされたブレークポイントを削除することも[IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)します。  
  
## <a name="see-also"></a>関連項目  
 [デバッガーのイベントの呼び出し](../../extensibility/debugger/calling-debugger-events.md)

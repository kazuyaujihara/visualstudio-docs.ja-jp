---
title: ブレークポイントの作成 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, creating
- debugging [Debugging SDK], creating breakpoints
ms.assetid: 6f9f87bb-192e-45e0-9a7a-ffe729e87f7d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c682920c7e879d65dfddd3b4fee17a0f20b26b21
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63411272"
---
# <a name="create-a-breakpoint"></a>ブレークポイントを作成します。
次に、ブレークポイントを作成するプロセスについて説明します。

## <a name="methods-in-breakpoint-creation"></a>ブレークポイントの作成方法
 ブレークポイントをバインドするために必要なモジュールが読み込まれるときに、セッション デバッグ マネージャー (SDM) は、次のメソッドを呼び出します。

1. [IDebugPendingBreakpoint2::Enable](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)

2. [IDebugPendingBreakpoint2::Virtualize](../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md)

3. [IDebugPendingBreakpoint2::CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)

    > [!NOTE]
    > **CanBind**からブレークポイントを行うときにのみ呼び出される、**ブレークポイント**ウィンドウ。

4. [IDebugPendingBreakpoint2::Bind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)

5. [IDebugPendingBreakpoint2::EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)

## <a name="see-also"></a>関連項目
- [デバッガー イベントを呼び出す](../../extensibility/debugger/calling-debugger-events.md)
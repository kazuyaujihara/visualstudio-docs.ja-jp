---
title: IDebugPendingBreakpoint2::GetState |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2::GetState
helpviewer_keywords:
- GetState method
- IDebugPendingBreakpoint2::GetState method
ms.assetid: e88d543f-2e83-4ba7-86ca-f874e39955ff
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 84ee5c48a74fa9ed707cc55be3cbc1ab49940552
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347772"
---
# <a name="idebugpendingbreakpoint2getstate"></a>IDebugPendingBreakpoint2::GetState
保留中のブレークポイントの状態を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetState( 
   PENDING_BP_STATE_INFO* pState
);
```

```csharp
int GetState( 
   PENDING_BP_STATE_INFO[] pState
);
```

## <a name="parameters"></a>パラメーター
`pState`\
[入力、出力]A [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md)構造体の保留中のブレークポイントの説明が入力されます。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md)
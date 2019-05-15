---
title: IDebugBoundBreakpoint2::GetHitCount |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBoundBreakpoint2::GetHitCount
helpviewer_keywords:
- GetHitCount method
- IDebugBoundBreakpoint2::GetHitCount method
ms.assetid: 23481f37-047c-41d2-8286-4da1f4084961
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e173f1f448cba6ee3ed3ab7a6176089996e48e4a
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65614745"
---
# <a name="idebugboundbreakpoint2gethitcount"></a>IDebugBoundBreakpoint2::GetHitCount
このバインドされたブレークポイントの現在のヒット カウントを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetHitCount( 
   DWORD* pdwHitCount
);
```

```csharp
int GetHitCount( 
   out uint pdwHitCount
);
```

## <a name="parameters"></a>パラメーター
`pdwHitCount`\
[out]ヒット カウントを返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 返します`E_BP_DELETED`にバインドされたブレークポイント オブジェクトの状態が設定されてかどうか`BPS_DELETED`(の一部、 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)列挙型)。

## <a name="remarks"></a>Remarks
 ヒット カウントは、このブレークポイントは、セッションの現在の実行中に発生した回数です。

## <a name="see-also"></a>関連項目
- [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)
- [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)
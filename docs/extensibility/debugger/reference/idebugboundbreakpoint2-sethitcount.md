---
title: IDebugBoundBreakpoint2::SetHitCount |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBoundBreakpoint2::SetHitCount
helpviewer_keywords:
- SetHitCount method
- IDebugBoundBreakpoint2::SetHitCount method
ms.assetid: 8145d875-26b1-4049-a2a2-e7d3d7f4735f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ac7cbfa337bfdcf54d213b299badc9ca56d8dcba
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877290"
---
# <a name="idebugboundbreakpoint2sethitcount"></a>IDebugBoundBreakpoint2::SetHitCount
バインドされたブレークポイントのヒット カウントを設定します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetHitCount( 
   DWORD dwHitCount
);
```

```csharp
int SetHitCount( 
   uint dwHitCount
);
```

#### <a name="parameters"></a>パラメーター
 `dwHitCount`

 [in]ヒット カウントを設定します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 返します`E_BP_DELETED`にバインドされたブレークポイント オブジェクトの状態が設定されてかどうか`BPS_DELETED`(の一部、 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)列挙型)。

## <a name="remarks"></a>Remarks
 ヒット カウントは、このブレークポイントは、セッションの現在の実行中に発生した回数です。

 このメソッドは通常、このブレークポイントで現在のヒット カウントを更新するデバッグ エンジンによって呼び出されます。

## <a name="see-also"></a>関連項目
- [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)
- [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)
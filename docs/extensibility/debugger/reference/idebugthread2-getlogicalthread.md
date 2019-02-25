---
title: IDebugThread2::GetLogicalThread |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::GetLogicalThread
helpviewer_keywords:
- IDebugThread2::GetLogicalThread
ms.assetid: bce6230e-41d4-49b7-a050-2dde5efb6805
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 99e8dbd78ef262479fbc8405b77fa0cf53f8087a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723293"
---
# <a name="idebugthread2getlogicalthread"></a>IDebugThread2::GetLogicalThread
デバッグ エンジンは、このメソッドを実装していません。

## <a name="syntax"></a>構文

```cpp
HRESULT GetLogicalThread( 
   IDebugStackFrame2*     pStackFrame,
   IDebugLogicalThread2** ppLogicalThread
);
```

```csharp
int GetLogicalThread( 
   IDebugStackFrame2        pStackFrame,
   out IDebugLogicalThread2 ppLogicalThread
);
```

#### <a name="parameters"></a>パラメーター
 `pStackFrame`

 [in][IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)スタック フレームを表すオブジェクト。

 `ppLogicalThread`

 [out]返します、`IDebugLogicalThread2`関連付けられた論理スレッドを表すインターフェイスです。 デバッグ エンジンの実装は、null 値にこれを設定する必要があります。

## <a name="return-value"></a>戻り値
 デバッグ エンジン実装を常に戻り`E_NOTIMPL`します。

## <a name="see-also"></a>関連項目
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
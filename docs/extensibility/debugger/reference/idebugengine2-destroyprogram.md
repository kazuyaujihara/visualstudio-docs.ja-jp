---
title: IDebugEngine2::DestroyProgram |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::DestroyProgram
helpviewer_keywords:
- IDebugEngine2::DestroyProgram
ms.assetid: 0c9e2698-c70f-4770-a7bb-39650e9c3a1f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f626005621604d367f5878e36899aa2ff46114ee
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678450"
---
# <a name="idebugengine2destroyprogram"></a>IDebugEngine2::DestroyProgram
指定されたプログラムが正しく終了になっていると、DE、プログラムに対するすべての参照をクリーンアップするデバッグ エンジン (DE) を通知し、送信プログラムは、イベントを破棄します。

## <a name="syntax"></a>構文

```cpp
HRESULT DestroyProgram( 
   IDebugProgram2* pProgram
);
```

```cpp
int DestroyProgram( 
   IDebugProgram2 pProgram
);
```

#### <a name="parameters"></a>パラメーター
 `pProgram`

 [in][IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)になって終了されたプログラムを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドが呼び出された後、DE 後に、送信、 [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)イベントをセッション デバッグ マネージャー (SDM)。

 このメソッドが実装されていません (返します`E_NOTIMPL`)、DE がデバッグ中のプログラムと同じプロセスで実行する場合。 このメソッドは、DE が、SDM と同じプロセスで実行する場合にのみ実装されます。

## <a name="see-also"></a>関連項目
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
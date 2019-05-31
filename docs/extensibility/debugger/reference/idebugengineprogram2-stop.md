---
title: IDebugEngineProgram2::Stop |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineProgram2::Stop
helpviewer_keywords:
- IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ba93c88eb3d7e996b2a5f19dda605653af090c94
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345214"
---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
このプログラムで実行されているすべてのスレッドを停止します。

## <a name="syntax"></a>構文

```cpp
HRESULT Stop( 
   void 
);
```

```csharp
int Stop();
```

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 複数のプログラムの環境でこのプログラムをデバッグするときに、このメソッドが呼び出されます。 他のプログラムから stopping イベントが受信したときに、このメソッドは、このプログラムで呼び出されます。 このメソッドの実装を非同期にする必要があります。すべてのスレッドがこのメソッドが戻る前に停止する必要あります。 このメソッドの実装を呼び出す可能性があります、 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)このプログラムのメソッド。

 このメソッドへの応答では、デバッグ イベントは送信されません。

## <a name="see-also"></a>関連項目
- [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)
- [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)
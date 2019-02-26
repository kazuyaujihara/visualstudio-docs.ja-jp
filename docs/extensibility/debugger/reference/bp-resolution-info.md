---
title: BP_RESOLUTION_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_RESOLUTION_INFO
helpviewer_keywords:
- BP_RESOLUTION_INFO structure
ms.assetid: ba0c162a-61e8-4a0b-811f-4c1d8a5d82f0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 79104bf245221c14a27593665c1a4b2cd8cedaa0
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707225"
---
# <a name="bpresolutioninfo"></a>BP_RESOLUTION_INFO
コードのブレークポイントまたは データ ブレークポイントのバインドされたブレークポイント情報について説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct _BP_RESOLUTION_INFO {
    BPRESI_FIELDS          dwFields;
    BP_RESOLUTION_LOCATION bpResLocation;
    IDebugProgram2*        pProgram;
    IDebugThread2*         pThread;
} BP_RESOLUTION_INFO;
```

```csharp
public struct BP_RESOLUTION_INFO {
    public uint                   dwFields;
    public BP_RESOLUTION_LOCATION bpResLocation;
    public IDebugProgram2         pProgram;
    public IDebugThread2          pThread;
};
```

## <a name="members"></a>メンバー
`dwFields` フラグのコレクション、 [BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)フィールドを指定する列挙値を入力します。

`bpResLocation` [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)コードまたはデータ内のブレークポイントの位置を指定する構造体。

`pProgram` [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)ブレークポイントのエラーが発生したアプリケーションを表すオブジェクト。

`pThread` [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)ブレークポイントのエラーを格納しているアプリケーションが実行されているスレッドを表すオブジェクト。

## <a name="remarks"></a>Remarks
この構造体がによって返される[GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)します。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
- [BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)
- [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)

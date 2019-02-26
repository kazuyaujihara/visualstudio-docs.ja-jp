---
title: IDebugProgram2::CauseBreak |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::CauseBreak
helpviewer_keywords:
- IDebugProgram2::CauseBreak
ms.assetid: 07d353fc-68ab-4297-a18f-3d3c7a80e121
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 06b392dd10c364e746f592a4d0ffd9ac32ca7df9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720209"
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
プログラムが次の実行を停止する要求は時間を実行するには、そのスレッド試行のいずれかです。

## <a name="syntax"></a>構文

```cpp
HRESULT CauseBreak( 
   void 
);
```

```csharp
int CauseBreak();
```

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)次に、プログラムはこのメソッドが呼び出された後にコードを実行しようとしたときにイベントが送信されます。

 メソッドは必ずしもプログラムが停止するまで待たずにすぐに返します点で、このメソッドは非同期です。

## <a name="see-also"></a>関連項目
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)
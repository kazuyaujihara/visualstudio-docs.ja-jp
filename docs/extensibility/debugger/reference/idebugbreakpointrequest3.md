---
title: IDebugBreakpointRequest3 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointRequest3
helpviewer_keywords:
- IDebugBreakpointRequest3
ms.assetid: 8a042beb-b319-48e3-b3c8-9c8336ab371b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9101f1c2faeedf8b08b3b11044eaa22f6c6d512a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66352875"
---
# <a name="idebugbreakpointrequest3"></a>IDebugBreakpointRequest3
このインターフェイスは、作成し、任意の種類のブレークポイントをバインドするために必要な情報を表します。 拡張機能は[IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)します。

## <a name="syntax"></a>構文

```
IDebugBreakpointRequest3 : IDebugBreakpointRequest2
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 セッション デバッグ マネージャー (SDM) は、通常、このインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 デバッグ エンジン (DE) 呼び出すことによってこのインターフェイスにアクセスする[QueryInterface](/cpp/atl/queryinterface)への呼び出しで受け取った IDebugBreakpointRequest2 インターフェイスで[CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 継承されたメソッドだけでなく[IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)、`IDebugBreakpointRequest3`インターフェイスは、次のメソッドを公開します。

|メソッド|説明|
|------------|-----------------|
|[GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md)|このブレークポイントの要求を記述するブレークポイント要求情報を取得します。|

## <a name="remarks"></a>Remarks
 DE に追加情報を提供するこのインターフェイスを使用、 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)構造体。 この追加の情報には、DE のベンダーの ID (GUID の形式) で、トレース ポイントの名前やブレークポイント制約の名前が含まれています。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
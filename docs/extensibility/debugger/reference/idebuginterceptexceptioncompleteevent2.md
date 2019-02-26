---
title: IDebugInterceptExceptionCompleteEvent2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugInterceptExceptionCompleteEvent2
helpviewer_keywords:
- IDebugInterceptExceptionCompleteEvent2
ms.assetid: 8ebc256b-5428-4ed6-a505-6aedc8242b8e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f3bd87a4ae370690a5b055a1c3033d336385b86d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56711463"
---
# <a name="idebuginterceptexceptioncompleteevent2"></a>IDebugInterceptExceptionCompleteEvent2
このインターフェイスは、DE には、傍受したイベントの処理が完了したときにデバッグ エンジン (DE) によってセッション デバッグ マネージャー (SDM) に送信されます。

## <a name="syntax"></a>構文

```
IDebugInterceptExceptionCompleteEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 DE、傍受した例外の処理が完了したことを報告するには、このインターフェイスを実装します。 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)このインターフェイスと同じオブジェクトでインターフェイスを実装する必要があります。 SDM を使用して[QueryInterface](/cpp/atl/queryinterface)にアクセスする、`IDebugEvent2`インターフェイス。

## <a name="notes-for-callers"></a>呼び出し元のノート
 デは作成し、受信済みの例外の完了を報告するには、このイベント オブジェクトを送信します。 使用して、イベントが送信される、 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)デバッグ中のプログラムに添付するときに、SDM によって指定されたコールバック関数。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 `IDebugInterceptExceptionCompleteEvent2`インターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetInterceptCookie](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2-getinterceptcookie.md)|処理済みの例外に関連付けられている一意の値を返します。|

## <a name="remarks"></a>Remarks
 このイベントで送信される[InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)そのメソッドが完了すると正常に傍受した例外を処理します。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)
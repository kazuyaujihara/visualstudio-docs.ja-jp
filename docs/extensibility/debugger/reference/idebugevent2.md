---
title: IDebugEvent2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7e70767bab6453f3c3d96b58c8be049a832dc6ad
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920195"
---
# <a name="idebugevent2"></a>IDebugEvent2
このインターフェイスは、ブレークポイントで停止するなどの重要なデバッグ情報とデバッグ メッセージなどの致命的でない情報の両方の通信に使用されます。

## <a name="syntax"></a>構文

```
IDebugEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 デバッグ エンジン (DE) とカスタム ポート サプライヤーは、他のすべてのイベント インターフェイスと同じオブジェクトでこのインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 インターフェイスに指定された ID (IID) 引数を使用して[イベント](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)または[イベント](../../../extensibility/debugger/reference/idebugportevents2-event.md)、セッション デバッグ マネージャー (SDM) を呼び出す[QueryInterface](/cpp/atl/queryinterface)上、`IDebugEvent2`インターフェイスを取得するには適切なイベントのインターフェイスです。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IDebugEvent2`します。

|メソッド|説明|
|------------|-----------------|
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|このデバッグ イベントの属性を取得します。|

## <a name="remarks"></a>Remarks
 特定のイベント インターフェイスなど[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)IDebugEvent2 インターフェイスから派生していないと同じオブジェクトに個別のインターフェイスとして実装が代わりに、`IDebugEvent2`します。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
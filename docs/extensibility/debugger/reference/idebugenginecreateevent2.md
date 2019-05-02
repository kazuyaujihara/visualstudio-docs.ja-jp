---
title: IDebugEngineCreateEvent2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineCreateEvent2
helpviewer_keywords:
- IDebugEngineCreateEvent2 interface
ms.assetid: 37c0a841-1c8d-4802-a990-36b54bca3ef7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eec2d1dd536b70432b761d613389acdac80cd6d5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62921272"
---
# <a name="idebugenginecreateevent2"></a>IDebugEngineCreateEvent2
デバッグ エンジン (DE) では、DE のインスタンスが作成されたときに、このインターフェイスをセッション デバッグ マネージャー (SDM) に送信します。

## <a name="syntax"></a>構文

```
IDebugEngineCreateEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 デが通常の操作の一部としてこのインターフェイスを実装します。 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)このインターフェイスと同じオブジェクトでインターフェイスを実装する必要があります (、SDM を使用して、`QueryInterface`メソッドにアクセスする、`IDebugEvent2`インターフェイス)。

## <a name="notes-for-callers"></a>呼び出し元のノート
 デは作成し、DE がインスタンス化されたときに、このイベント オブジェクトを送信します。 使用して、イベントが送信される、 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)デバッグ中のプログラムに添付するときに、SDM によって指定されたコールバック関数。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IDebugEngineCreateEvent2`します。

|メソッド|説明|
|------------|-----------------|
|[GetEngine](../../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)|新しく作成されたデバッグ エンジン (DE) を表すオブジェクトを取得します。|

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
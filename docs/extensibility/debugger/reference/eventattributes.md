---
title: 複数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 58417471e37dd335c2fa751492f2db357274417a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686900"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
イベントの属性を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_EVENTATTRIBUTES {
    EVENT_ASYNCHRONOUS          = 0x0000,
    EVENT_SYNCHRONOUS           = 0x0001,
    EVENT_STOPPING              = 0x0002,
    EVENT_ASYNC_STOP            = 0x0002,
    EVENT_SYNC_STOP             = 0x0003,
    EVENT_IMMEDIATE             = 0x0004,
    EVENT_EXPRESSION_EVALUATION = 0x0008
};
typedef DWORD EVENTATTRIBUTES;
```

```csharp
public enum enum_EVENTATTRIBUTES {
    EVENT_ASYNCHRONOUS          = 0x0000,
    EVENT_SYNCHRONOUS           = 0x0001,
    EVENT_STOPPING              = 0x0002,
    EVENT_ASYNC_STOP            = 0x0002,
    EVENT_SYNC_STOP             = 0x0003,
    EVENT_IMMEDIATE             = 0x0004,
    EVENT_EXPRESSION_EVALUATION = 0x0008
};
```

## <a name="members"></a>メンバー
EVENT_ASYNCHRONOUS ことを示し、イベントは非同期イベントに応答する必要はありません。

EVENT_SYNCHRONOUS イベントが同期的です。 あることを示します返信して[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)します。

EVENT_STOPPING は stopping イベントの実行であることを示します。 いずれかと組み合わせることは`EVENT_ASYNCHRONOUS`または`EVENT_SYNCHRONOUS`します。

EVENT_ASYNC_STOP では、非同期の停止イベントを示します。 現在、このようなイベントはありません。 このフラグは、単なるプレース ホルダーです。

EVENT_SYNC_STOP が同期の停止イベントを示します (の組み合わせ`EVENT_SYNCHRONOUS`と`EVENT_STOPPING`)。 この値は、停止イベントを送信するときにデバッグ エンジン (DE) によって使用されます。 呼び出しを使用して、返信があった[Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md)、[手順](../../../extensibility/debugger/reference/idebugprogram2-step.md)、または[続行](../../../extensibility/debugger/reference/idebugprogram2-continue.md)します。

EVENT_IMMEDIATE の IDE に即座に同期的に送信されるイベントを示します。 このフラグはその他のフラグのような`EVENT_ASYNCHRONOUS`、 `EVENT_SYNCHRONOUS`、または`EVENT_SYNC_STOP`イベントと応答のメカニズム (あれば) が既知であるファクトの種類を示します。

EVENT_EXPRESSION_EVALUATION イベントは、式の評価の結果です。

## <a name="remarks"></a>Remarks
これらの値が渡された、`dwAttrib`のパラメーター、[イベント](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)メソッド。

これらの値は、演算と組み合わせることがあります`OR`します。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)

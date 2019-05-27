---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
helpviewer_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 41a644c2e0fb36cd39d55bf853f8362033eec8a0
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212423"
---
# <a name="idebugengineprogram2watchforexpressionevaluationonthread"></a>IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
プログラムが停止された場合でも、特定のスレッドで発生する式の評価を許可 (または許可されていません)。

## <a name="syntax"></a>構文

```cpp
HRESULT WatchForExpressionEvaluationOnThread( 
   IDebugProgram2*       pOriginatingProgram,
   DWORD                 dwTid,
   DWORD                 dwEvalFlags,
   IDebugEventCallback2* pExprCallback,
   BOOL                  fWatch
);
```

```csharp
int WatchForExpressionEvaluationOnThread( 
   IDebugProgram2       pOriginatingProgram,
   uint                  dwTid,
   uint                  dwEvalFlags,
   IDebugEventCallback2 pExprCallback,
   int                   fWatch
);
```

## <a name="parameters"></a>パラメーター
`pOriginatingProgram`\
[in][IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)式の評価プログラムを表すオブジェクト。

`dwTid`\
[in]スレッドの識別子を指定します。

`dwEvalFlags`\
[in]フラグの組み合わせ、 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)評価を実行する方法を指定する列挙体。

`pExprCallback`\
[in][IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)式の評価中に発生するデバッグ イベントの送信に使用するオブジェクト。

`fWatch`\
[in]0 以外の場合 (`TRUE`)、式の評価で識別されるスレッドで使用できるように`dwTid`、それ以外の 0 (`FALSE`) そのスレッドで式の評価を許可されていません。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 セッション デバッグ マネージャー (SDM) がで識別される、プログラムを確認するときに、`pOriginatingProgram`パラメーターを指定する式を評価するこのメソッドを呼び出すことによって接続されている他のすべてのプログラムに通知します。

 1 つのプログラムに式の評価が原因で、コードの関数の評価またはいずれかの評価のため、別の実行が`IDispatch`プロパティ。 このため、このメソッドは、式の評価を実行して完了場合でも、このプログラムでは、スレッドを停止する可能性がありますを使用します。

## <a name="see-also"></a>関連項目
- [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)
- [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
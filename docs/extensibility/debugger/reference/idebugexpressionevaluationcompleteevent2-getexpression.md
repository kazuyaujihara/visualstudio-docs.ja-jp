---
title: IDebugExpressionEvaluationCompleteEvent2::GetExpression |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionEvaluationCompleteEvent2::GetExpression
helpviewer_keywords:
- IDebugExpressionEvaluationCompleteEvent2::GetExpression
ms.assetid: faf6b2dd-2afd-4852-b21c-7e8d3130e141
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bb413457b9e84d57079d9c5efa3369ddad608934
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707693"
---
# <a name="idebugexpressionevaluationcompleteevent2getexpression"></a>IDebugExpressionEvaluationCompleteEvent2::GetExpression
元の式を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetExpression( 
   IDebugExpression2** ppExpr
);
```

```csharp
int GetExpression( 
   out IDebugExpression2 ppExpr
);
```

#### <a name="parameters"></a>パラメーター
 `ppExpr`

 [out]返します、 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)が解析された式を表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドの呼び出しで作成されたオブジェクトを返します、 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)
- [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)
- [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)
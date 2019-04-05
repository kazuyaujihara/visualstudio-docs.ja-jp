---
title: IDebugStackFrame2::GetExpressionContext | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetExpressionContext
helpviewer_keywords:
- IDebugStackFrame2::GetExpressionContext
ms.assetid: a2604e6a-502d-473b-868f-b11ac64c7a35
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7aea3543401faa1e7a6fd3ab2d3de073b5e6b3bf
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976734"
---
# <a name="idebugstackframe2getexpressioncontext"></a>IDebugStackFrame2::GetExpressionContext
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

スタック フレームとスレッドの現在のコンテキストで式の評価の評価コンテキストを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetExpressionContext (   
   IDebugExpressionContext2** ppExprCxt  
);  
```  
  
```csharp  
int GetExpressionContext (   
   out IDebugExpressionContext2 ppExprCxt  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppExprCxt`  
 [out]返します、 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)式の評価のコンテキストを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 一般に、式の評価コンテキストは、式の評価を実行するためのスコープとして考えることができます。 呼び出す、 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)式を解析し、結果を呼び出すメソッド[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)または[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)解析された式を評価するメソッド。  
  
## <a name="see-also"></a>関連項目  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)

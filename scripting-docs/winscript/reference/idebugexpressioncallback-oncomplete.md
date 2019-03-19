---
title: IDebugExpressionCallBack::onComplete |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpressionCallBack.onComplete
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugExpressionCallBack::onComplete
ms.assetid: d0b89db3-38e7-44e0-93fe-60205f9149dd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7bcadc8c9d4fe8c1991db19483673a36bf5c0b90
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144356"
---
# <a name="idebugexpressioncallbackoncomplete"></a>IDebugExpressionCallBack::onComplete
式の評価が完了したことを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT onComplete();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドには、パラメーターはありません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 式の評価が完了すると、このメソッドが呼び出されます。 `IDebugExpression::GetResultAsString`メソッドは、このイベント ハンドラー内から呼び出すことができます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExpressionCallBack インターフェイス](../../winscript/reference/idebugexpressioncallback-interface.md)   
 [IDebugExpression::GetResultAsString](../../winscript/reference/idebugexpression-getresultasstring.md)
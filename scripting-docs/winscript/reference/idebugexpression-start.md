---
title: IDebugExpression::Start |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpression.Start
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpression::Start
ms.assetid: a7af3470-62b5-40f0-987d-63b6b22538b3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e80f3fb8087d39c76f59cf5c6bc8719c1cbaf5e4
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58145045"
---
# <a name="idebugexpressionstart"></a>IDebugExpression::Start
式の評価を開始します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Start(  
   IDebugExpressionCallBack*  pdecb  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pdecb`  
 [in]式の評価が完了したことを示すためのコールバック。 このパラメーターが場合`NULL`イベントが発生しないと、クライアントを使用して式の状態をポーリングする必要があります、`QueryIsComplete`します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、式の評価を開始します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)   
 [IDebugExpression インターフェイス](../../winscript/reference/idebugexpression-interface.md)
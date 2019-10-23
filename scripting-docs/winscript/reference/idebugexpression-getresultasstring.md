---
title: 'IDebugExpression:: GetResultAsString |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpression.GetResultAsString
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpression::GetResultAsString
ms.assetid: edadd2ad-9369-4878-bf87-cea15be9f363
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 56b8f637744227763f55b7c024745d7ae4448b40
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573523"
---
# <a name="idebugexpressiongetresultasstring"></a>IDebugExpression::GetResultAsString
式の評価結果を文字列として返し、操作の戻り値を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetResultAsString(  
   HRESULT*  phrResult,  
   BSTR*     pbstrResult  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `phrResult`  
 入出力操作の戻り値。  
  
 `pbstrResult`  
 入出力式の評価の結果。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_PENDING`|操作は保留中です。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、式の評価結果を文字列として返し、操作の `HRESULT` を返します。  
  
 このメソッドは `S_OK` を返し、`Abort` が操作を中止する場合は `E_ABORT` を返し `phrResult` を返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExpression インターフェイス](../../winscript/reference/idebugexpression-interface.md)
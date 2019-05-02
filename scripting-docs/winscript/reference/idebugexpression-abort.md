---
title: IDebugExpression::Abort |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpression.Abort
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpression::Abort
ms.assetid: dbdb63c1-6c4a-4cef-bb40-1843495ae167
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cfaee56fffc7b28d04979f39b840d0b07cde2e08
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62978459"
---
# <a name="idebugexpressionabort"></a>IDebugExpression::Abort
式を停止します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Abort();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドには、パラメーターはありません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、できるだけ早い機会に、式の評価を停止します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExpression インターフェイス](../../winscript/reference/idebugexpression-interface.md)   
 [IDebugExpression::Start](../../winscript/reference/idebugexpression-start.md)
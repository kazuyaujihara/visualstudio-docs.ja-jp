---
title: IBindEventHandler::BindHandler |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IBindEventHandler.BindHandler
apilocation:
- scrobj.dll
helpviewer_keywords:
- IBindEventHandler::BindHandler
ms.assetid: 87909828-2224-4bb1-a6c9-dfe715ac4c9b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 01372766eb434efe73f47b265c7984bab48ea164
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58146059"
---
# <a name="ibindeventhandlerbindhandler"></a>IBindEventHandler::BindHandler
イベントをオブジェクトにバインドします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT BindHandler(  
   LPCOLESTR   pstrEvent,  
   IDispatch*  pdisp  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstrEvent`  
 [in]処理するイベントを指定します。  
  
 `pdisp`  
 [in]イベントを処理するオブジェクトを指定します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、イベントをオブジェクトにバインドします。  
  
## <a name="see-also"></a>関連項目  
 [IBindEventHandler インターフェイス](../../winscript/reference/ibindeventhandler-interface.md)
---
title: 'IBindEventHandler:: BindHandler |Microsoft Docs'
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
ms.openlocfilehash: 160020832509c9fb2aa95c095148127228a92e17
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572573"
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
 から処理するイベントを指定します。  
  
 `pdisp`  
 からイベントを処理するオブジェクトを指定します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、イベントをオブジェクトにバインドします。  
  
## <a name="see-also"></a>関連項目  
 [IBindEventHandler インターフェイス](../../winscript/reference/ibindeventhandler-interface.md)
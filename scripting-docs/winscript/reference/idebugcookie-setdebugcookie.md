---
title: 'IDebugCookie:: SetDebugCookie |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugCookie.SetDebugCookie
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugCookie::SetDebugCookie
ms.assetid: 9cba3b05-ff81-4fb0-9382-e9338cb9192d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 664939d0b91b8dbbf87dbff2978064811ffee486
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573188"
---
# <a name="idebugcookiesetdebugcookie"></a>IDebugCookie::SetDebugCookie
デバッグアプリケーションクッキーを設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetDebugCookie(  
   DWORD  dwDebugAppCookie  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwDebugAppCookie`  
 からデバッグアプリケーションを識別するクッキー。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、複数のデバッガーがプロセスにアタッチできるようにする、デバッグアプリケーションクッキーを設定します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugCookie インターフェイス](../../winscript/reference/idebugcookie-interface.md)
---
title: IDebugCookie::SetDebugCookie |Microsoft Docs
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
ms.openlocfilehash: c83c1331a95e48afa02b0b37557ca5bd042261d7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974476"
---
# <a name="idebugcookiesetdebugcookie"></a>IDebugCookie::SetDebugCookie
アプリケーションのデバッグの cookie を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetDebugCookie(  
   DWORD  dwDebugAppCookie  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwDebugAppCookie`  
 [in]デバッグ アプリケーションを識別するクッキー。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、1 つ以上のデバッガーをアタッチするプロセスは、デバッグのアプリケーションの cookie を設定します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugCookie インターフェイス](../../winscript/reference/idebugcookie-interface.md)
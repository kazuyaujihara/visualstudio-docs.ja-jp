---
title: IMachineDebugManager::RemoveApplication |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IMachineDebugManager.RemoveApplication
apilocation:
- scrobj.dll
helpviewer_keywords:
- IMachineDebugManager::RemoveApplication
ms.assetid: 873509ce-e638-484a-b2a2-489a8ce7dbfe
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ee70097ab87406d6ad39b244bdec61a72aea836
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977553"
---
# <a name="imachinedebugmanagerremoveapplication"></a>IMachineDebugManager::RemoveApplication
実行中のアプリケーションを削除します。 アプリケーションの一覧。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT RemoveApplication(  
   DWORD  dwAppCookie  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwAppCookie`  
 [in]アプリケーションは、アプリケーションの一覧に追加されたときに提供されるクッキー。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、プロセス デバッグ マネージャーたびに`IProcessDebugManager::RemoveApplication`が呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [IMachineDebugManager::AddApplication](../../winscript/reference/imachinedebugmanager-addapplication.md)   
 [IMachineDebugManager インターフェイス](../../winscript/reference/imachinedebugmanager-interface.md)   
 [IProcessDebugManager::RemoveApplication](../../winscript/reference/iprocessdebugmanager-removeapplication.md)
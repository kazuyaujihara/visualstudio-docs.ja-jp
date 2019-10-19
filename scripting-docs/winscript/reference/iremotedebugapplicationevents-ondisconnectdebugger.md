---
title: 'IRemoteDebugApplicationEvents:: Onオフデバッガー |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEvents.OnDisconnectDebugger
apilocation:
- jscript.dll
helpviewer_keywords:
- IRemoteDebugApplicationEvents::OnDisconnectDebugger
ms.assetid: ea11cde0-1484-4181-a5dd-a1f6cf788892
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53e26da46fcdca0db0c8a652a091e95cd83789cd
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575584"
---
# <a name="iremotedebugapplicationeventsondisconnectdebugger"></a>IRemoteDebugApplicationEvents::OnDisconnectDebugger
デバッガーの切断イベントを処理します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnDisconnectDebugger();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドはパラメーターを受け取りません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、デバッガーの切断イベントを処理します。  
  
## <a name="see-also"></a>関連項目  
 [IRemoteDebugApplicationEvents インターフェイス](../../winscript/reference/iremotedebugapplicationevents-interface.md)
---
title: 'IRemoteDebugApplicationThread:: GetSuspendCount |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.GetSuspendCount
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::GetSuspendCount
ms.assetid: 37f9936c-fd7c-412d-9a7f-628ca3a90438
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53370d3489f5bb3c8dc8dfe9349ccc32ca923f05
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575234"
---
# <a name="iremotedebugapplicationthreadgetsuspendcount"></a>IRemoteDebugApplicationThread::GetSuspendCount
スレッドの中断回数を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetSuspendCount(  
   DWORD*  pdwCount  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pdwCount`  
 入出力スレッドの中断カウント。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、スレッドの中断回数を返します。  
  
## <a name="see-also"></a>関連項目  
 [IRemoteDebugApplicationThread インターフェイス](../../winscript/reference/iremotedebugapplicationthread-interface.md)
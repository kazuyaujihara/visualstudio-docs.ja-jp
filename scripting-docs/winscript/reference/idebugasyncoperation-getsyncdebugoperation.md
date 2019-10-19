---
title: 'IDebugAsyncOperation:: GetSyncDebugOperation |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugAsyncOperation.GetSyncDebugOperation
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugAsyncOperation::GetSyncDebugOperation
ms.assetid: ff89a3bc-57d7-4cb9-9818-8d73ed71af73
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8d732b732681216c0e9eecec7f448bf263376d8c
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573271"
---
# <a name="idebugasyncoperationgetsyncdebugoperation"></a>IDebugAsyncOperation::GetSyncDebugOperation
このオブジェクトに関連付けられている同期デバッグ操作を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetSyncDebugOperation(  
   IDebugSyncOperation**  ppsdo  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppsdo`  
 入出力このオブジェクトに関連付けられている同期デバッグ操作。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、このオブジェクトに関連付けられている同期デバッグ操作を返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugAsyncOperation インターフェイス](../../winscript/reference/idebugasyncoperation-interface.md)
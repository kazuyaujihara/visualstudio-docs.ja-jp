---
title: 'IDebugSyncOperation:: In進捗 Abort |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSyncOperation.InProgressAbort
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugSyncOperation::InProgressAbort
ms.assetid: bfd0889c-b627-4843-b1c6-b6b918f42d61
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 40974c738c071e52648297ac90a0ab89d9681435
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576668"
---
# <a name="idebugsyncoperationinprogressabort"></a>IDebugSyncOperation::InProgressAbort
別のスレッドで実行中の操作を取り消します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT InProgressAbort();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドはパラメーターを受け取りません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_NOTIMPL`|操作を取り消すことはできません。|  
|`E_ABORT`|操作を完了できませんでした。|  
  
## <a name="remarks"></a>Remarks  
 プロセスデバッグマネージャーは、デバッガースレッド内からこのメソッドを呼び出して、別のスレッドで実行中の操作を取り消します。  
  
 @No__t_0 メソッドが操作を完了できない場合は、できるだけ早く `E_ABORT` を返します。 このメソッドは、操作を取り消すことができない場合に `E_NOTIMPL` を返すことができます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugSyncOperation インターフェイス](../../winscript/reference/idebugsyncoperation-interface.md)
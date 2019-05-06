---
title: IDebugSyncOperation::Execute |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSyncOperation.Execute
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugSyncOperation::Execute
ms.assetid: a45b8c7d-c51a-4098-877f-fbec2f1f6947
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2bc204169ff94a240e363eb8caa35ec8c7de9be
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63004879"
---
# <a name="idebugsyncoperationexecute"></a>IDebugSyncOperation::Execute
同期的に、操作を実行し、返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Execute(  
   IUnknown**  ppunkResult  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppunkResult`  
 [out]操作によって返されるオブジェクトのパラメーターです。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_ABORT`|呼び出して、操作が中止されました、`IDebugSyncOperation::InProgressAbort`メソッド。|  
  
## <a name="remarks"></a>Remarks  
 ターゲット スレッドの呼び出しで、プロセス デバッグ マネージャー、`Execute`メソッド同期的にします。  
  
## <a name="see-also"></a>関連項目  
 [IDebugSyncOperation インターフェイス](../../winscript/reference/idebugsyncoperation-interface.md)
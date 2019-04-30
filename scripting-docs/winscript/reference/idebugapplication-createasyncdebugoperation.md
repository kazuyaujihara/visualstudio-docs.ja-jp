---
title: IDebugApplication::CreateAsyncDebugOperation |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.CreateAsyncDebugOperation
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::CreateAsyncDebugOperation
ms.assetid: bc32b101-6364-4498-8458-bd5f3ab5ad94
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c60c84dbd3be9248e2bd075e65d53f7f9361d0b5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62991013"
---
# <a name="idebugapplicationcreateasyncdebugoperation"></a>IDebugApplication::CreateAsyncDebugOperation
指定された同期デバッグ操作への非同期アクセスを提供します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CreateAsyncDebugOperation(  
   IDebugSyncOperation*    psdo,  
   IDebugAsyncOperation**  ppado  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `psdo`  
 [in]同期デバッグ操作オブジェクト。  
  
 `ppado`  
 [out]非同期デバッグ操作オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、式の評価を非同期的にデバッガー スレッドに明示的に同期せずに、言語エンジンを使用します。 詳細については、次を参照してください。 [IDebugSyncOperation インターフェイス](../../winscript/reference/idebugsyncoperation-interface.md)と[IDebugAsyncOperation インターフェイス](../../winscript/reference/idebugasyncoperation-interface.md)します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplication インターフェイス](../../winscript/reference/idebugapplication-interface.md)   
 [IDebugSyncOperation インターフェイス](../../winscript/reference/idebugsyncoperation-interface.md)   
 [IDebugAsyncOperation インターフェイス](../../winscript/reference/idebugasyncoperation-interface.md)
---
title: IRemoteDebugApplication::GetDebugger |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.GetDebugger
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::GetDebugger
ms.assetid: 3d173b86-9281-4a3c-9550-d79408fd50ba
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba28af068bae6baa3031dde346fa0157e8e1ce6d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155655"
---
# <a name="iremotedebugapplicationgetdebugger"></a>IRemoteDebugApplication::GetDebugger
アプリケーションに接続されている現在のデバッガーを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDebugger(  
   IApplicationDebugger**  pad  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pad`  
 [out]現在のデバッガーは、アプリケーションに接続します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、アプリケーションに接続されている現在のデバッガーを返します。  
  
## <a name="see-also"></a>関連項目  
 [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)   
 [IRemoteDebugApplication インターフェイス](../../winscript/reference/iremotedebugapplication-interface.md)
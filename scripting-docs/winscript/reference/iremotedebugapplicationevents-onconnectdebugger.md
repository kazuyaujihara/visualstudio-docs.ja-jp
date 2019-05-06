---
title: IRemoteDebugApplicationEvents::OnConnectDebugger |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEvents.OnConnectDebugger
apilocation:
- jscript.dll
helpviewer_keywords:
- IRemoteDebugApplicationEvents::OnConnectDebugger
ms.assetid: 8c9c19b8-5426-4643-83e6-b68803ff69c4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d720df480133e10b1556939531d5d9a8427d23f3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62943657"
---
# <a name="iremotedebugapplicationeventsonconnectdebugger"></a>IRemoteDebugApplicationEvents::OnConnectDebugger
デバッガーがハンドルは、イベントを接続します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnConnectDebugger(  
   IApplicationDebugger*  pad  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pad`  
 [in]新しく接続したデバッガーです。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、デバッガーを処理するイベントを接続します。  
  
## <a name="see-also"></a>関連項目  
 [IRemoteDebugApplicationEvents インターフェイス](../../winscript/reference/iremotedebugapplicationevents-interface.md)
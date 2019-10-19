---
title: 'IScriptScriptlet レット:: SetEventName |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptScriptlet.SetEventName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptScriptlet::SetEventName
ms.assetid: 8787d58b-7deb-415b-b0e9-d2f0eb72dcf7
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5283646838f02cdc1c5ab27f63fd237d698fc6ed
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571899"
---
# <a name="iscriptscriptletseteventname"></a>IScriptScriptlet::SetEventName
スクリプトレットに関連付けられているイベントの名前を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetEventName(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `psz`  
 から@No__t_0 オブジェクトに関連付けられているイベント名を格納しているバッファー。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptScriptlet インターフェイス](../../winscript/reference/iscriptscriptlet-interface.md)
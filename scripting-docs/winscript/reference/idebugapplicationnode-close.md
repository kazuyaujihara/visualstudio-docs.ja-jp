---
title: IDebugApplicationNode::Close |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNode.Close
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationNode::Close
ms.assetid: ea8db480-2344-4c7b-960c-4fa97fa6c1b7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c634fd154c2470b1a154e5d1c9e97419a2e2e2b4
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58154833"
---
# <a name="idebugapplicationnodeclose"></a>IDebugApplicationNode::Close
によりこのアプリケーションはすべての参照を解放し、非アクティブな状態を入力します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Close();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドには、パラメーターはありません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 通常、アプリケーションの所有者は、アプリケーションの終了時にこのメソッドを呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationNode インターフェイス](../../winscript/reference/idebugapplicationnode-interface.md)
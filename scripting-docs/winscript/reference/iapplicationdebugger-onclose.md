---
title: IApplicationDebugger::onClose |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebugger.onClose
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebugger::onClose
ms.assetid: f3d6ca9f-6697-4d02-9d1a-16e3859bf282
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5e749c51769bd3344e144836937492fbb0a8fb58
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149641"
---
# <a name="iapplicationdebuggeronclose"></a>IApplicationDebugger::onClose
デバッグ アプリケーションの終了イベントを処理します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT onClose();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドには、パラメーターはありません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドが呼び出されます`IDebugApplication::Close`が呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [IApplicationDebugger インターフェイス](../../winscript/reference/iapplicationdebugger-interface.md)   
 [IDebugApplication::Close](../../winscript/reference/idebugapplication-close.md)
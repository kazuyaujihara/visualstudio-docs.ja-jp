---
title: IDebugAsyncOperationCallBack::onComplete |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugAsyncOperationCallBack.onComplete
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugAsyncOperationCallBack::onComplete
ms.assetid: d4023f5a-41f9-4948-b0dc-3317d61bb783
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f9e5532a55901d8e29addfee58594645440991f6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58151337"
---
# <a name="idebugasyncoperationcallbackoncomplete"></a>IDebugAsyncOperationCallBack::onComplete
結果は非同期デバッグ操作から使用できることを通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT onComplete();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドには、パラメーターはありません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドはから利用可能な結果を通知する`IDebugAsyncOperation`オブジェクト。 デバッガーのスレッドでイベントが発生します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugAsyncOperationCallBack インターフェイス](../../winscript/reference/idebugasyncoperationcallback-interface.md)   
 [IDebugAsyncOperation インターフェイス](../../winscript/reference/idebugasyncoperation-interface.md)
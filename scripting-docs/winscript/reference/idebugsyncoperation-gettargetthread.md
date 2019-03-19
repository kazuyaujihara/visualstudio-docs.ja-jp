---
title: IDebugSyncOperation::GetTargetThread |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSyncOperation.GetTargetThread
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugSyncOperation::GetTargetThread
ms.assetid: e6eeeb90-b5ed-4727-8434-fa3186c25013
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e270757ba26d61288a897bee4128317e6f4499cb
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58158647"
---
# <a name="idebugsyncoperationgettargetthread"></a>IDebugSyncOperation::GetTargetThread
この同期操作を行う対象のアプリケーションのスレッドを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetTargetThread(  
   IDebugApplicationThread**  ppatTarget  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppatTarget`  
 [out]この同期操作を行う対象のアプリケーション スレッドです。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、この同期操作を行う対象のアプリケーションのスレッドを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugSyncOperation インターフェイス](../../winscript/reference/idebugsyncoperation-interface.md)
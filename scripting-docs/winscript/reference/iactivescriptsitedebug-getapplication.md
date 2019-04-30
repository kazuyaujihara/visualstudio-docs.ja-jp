---
title: IActiveScriptSiteDebug::GetApplication |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.GetApplication
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::GetApplication
ms.assetid: 4400f1b1-3108-4a71-b1f1-43586fe1227c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75560ead40809c77e4768f8318d754a512e5d7ba
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992634"
---
# <a name="iactivescriptsitedebuggetapplication"></a>IActiveScriptSiteDebug::GetApplication
このスクリプトのサイトに関連付けられたデバッグ アプリケーション オブジェクトを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetApplication(  
   IDebugApplication**  ppda  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppda`  
 [out]スクリプト サイトに関連付けられたデバッグ アプリケーション オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_NOTIMPL`|ホストでは、デバッグを直接はサポートはありません。|  
  
## <a name="remarks"></a>Remarks  
 `GetApplication`メソッドは、各スクリプトが所属するアプリケーション オブジェクトを定義するスマート ホスト方法を提供します。 含むアプリケーションを取得しには、このメソッドを呼び出すスクリプト エンジンを試みる必要がある`IProcessDebugManager::GetDefaultApplication`これが失敗した場合。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSiteDebug インターフェイス](../../winscript/reference/iactivescriptsitedebug-interface.md)   
 [IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)
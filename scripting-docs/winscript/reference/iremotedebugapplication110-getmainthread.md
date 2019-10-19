---
title: 'IRemoteDebugApplication110:: GetMainThread |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110::GetMainThread
ms.assetid: 9982acc9-3d35-4dcf-8ca9-662469de4072
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff99c43f633da8454eb5fa32463886877e06ed72
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574120"
---
# <a name="iremotedebugapplication110getmainthread"></a>IRemoteDebugApplication110::GetMainThread
[SetSite](http://go.microsoft.com/fwlink/?LinkId=232439)を呼び出すホストのメインスレッドを返します。それ以外の場合は E_FAIL を返します。  
  
> [!IMPORTANT]
> [Iremotedebugapplication インターフェイス](../../winscript/reference/iremotedebugapplication-interface.md)は、PDM version 11.0 以上で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetMainThread([out] IRemoteDebugApplicationThread **ppThread);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppThread`  
 入出力メインの[Iremotedebugapplicationthread インターフェイス](../../winscript/reference/iremotedebugapplicationthread-interface.md)。  
  
## <a name="see-also"></a>関連項目  
 [Iremotedebugapplication インターフェイス](../../winscript/reference/iremotedebugapplication-interface.md)   
 [IRemoteDebugApplication110 インターフェイス](../../winscript/reference/iremotedebugapplication110-interface.md)
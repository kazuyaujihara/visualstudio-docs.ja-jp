---
title: IRemoteDebugApplication110::GetMainThread |Microsoft Docs
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
ms.openlocfilehash: 8a4b51d87f89d77bebf065ce5f52a297ada333d3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63383507"
---
# <a name="iremotedebugapplication110getmainthread"></a>IRemoteDebugApplication110::GetMainThread
呼び出すホストのメイン スレッドを返します[SetSite](http://go.microsoft.com/fwlink/?LinkId=232439)E_FAIL を返します。  
  
> [!IMPORTANT]
> [IRemoteDebugApplication インターフェイス](../../winscript/reference/iremotedebugapplication-interface.md)PDM v11.0 以降によって実装された以降には。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetMainThread([out] IRemoteDebugApplicationThread **ppThread);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppThread`  
 [out]メイン[IRemoteDebugApplicationThread インターフェイス](../../winscript/reference/iremotedebugapplicationthread-interface.md)します。  
  
## <a name="see-also"></a>関連項目  
 [IRemoteDebugApplication インターフェイス](../../winscript/reference/iremotedebugapplication-interface.md)   
 [IRemoteDebugApplication110 インターフェイス](../../winscript/reference/iremotedebugapplication110-interface.md)
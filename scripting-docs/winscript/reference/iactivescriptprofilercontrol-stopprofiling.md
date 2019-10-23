---
title: 'IActiveScriptProfilerControl:: StopProfiling |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.StopProfiling
apilocation:
- scrobj.dll
ms.assetid: 23b46ed6-a398-44c0-bc49-bf122e697cfe
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: da5900678093d57b3c995ac3bca8464ccd612fb2
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571539"
---
# <a name="iactivescriptprofilercontrolstopprofiling"></a>IActiveScriptProfilerControl::StopProfiling
スクリプトエンジンでのプロファイリングを停止します。 このメソッドは、profiler オブジェクトで[IActiveScriptProfilerCallback:: Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)を呼び出し、それを解放します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT StopProfiling(  
    [in] HRESULT hrShutdownReason);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hrShutdownReason`  
 からプロファイラーオブジェクトの[IActiveScriptProfilerCallback:: Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)メソッドにパラメーターとして渡される HRESULT。  
  
## <a name="return-value"></a>戻り値  
 HRESULT を返します。 次の値を指定できます。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|メソッドが成功しました。|  
|`ACTIVPROF_E_PROFILER_ABSENT`|プロファイルが有効になっていません。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerControl インターフェイス](../../winscript/reference/iactivescriptprofilercontrol-interface.md)
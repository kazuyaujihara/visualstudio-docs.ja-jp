---
title: 'IActiveScriptProfilerCallback:: Shutdown |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.Shutdown
apilocation:
- scrobj.dll
ms.assetid: 1281bf3c-d7d8-4ff5-9d8a-d1761fdb262e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: deecfe4134a4b0e18591823f194ceaf6d1eb0a14
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571646"
---
# <a name="iactivescriptprofilercallbackshutdown"></a>IActiveScriptProfilerCallback::Shutdown
スクリプトエンジンでプロファイリングが停止されたときに、プロファイラーオブジェクトに通知するために呼び出されます。 このようにして、profiler オブジェクトは必要に応じてクリーンアップルーチンを呼び出すことができます。 このメソッドは、スクリプトエンジンがシャットダウンしたとき、または[IActiveScriptProfilerCallback:: Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)の呼び出しが失敗したときに、スクリプトエンジンによっても呼び出されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Shutdown(  
    [in] HRESULT hrReason);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hrReason`  
 からシャットダウンの理由。 スクリプトエンジンがシャットダウン中の場合、`S_OK` が渡されます。 [IActiveScriptProfilerCallback:: Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)を呼び出すと、エラー hresult が返される場合は、hresult が渡されます。 それ以外の場合、この値は[IActiveScriptProfilerControl:: StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)から取得されます。  
  
## <a name="return-value"></a>戻り値  
 このメソッドの戻り値は、スクリプトエンジンによって無視されます。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerCallback インターフェイス](../../winscript/reference/iactivescriptprofilercallback-interface.md)
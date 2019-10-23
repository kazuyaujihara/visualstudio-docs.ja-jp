---
title: 'IActiveScriptProfilerCallback:: Initialize |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.Initialize
apilocation:
- scrobj.dll
ms.assetid: a257111e-a50b-4962-9dd6-c893d40f6985
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bbbd61d6b3c10dcfffe2df215cc5a60d685dd803
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576440"
---
# <a name="iactivescriptprofilercallbackinitialize"></a>IActiveScriptProfilerCallback::Initialize
プロファイリングをスクリプトエンジンで開始するときに、プロファイラーオブジェクトを初期化するために呼び出されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Initialize(  
    [in] DWORD dwContext);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwContext`  
 から[IActiveScriptProfilerControl:: StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md)に渡される4バイトの値。  
  
## <a name="return-value"></a>戻り値  
 HRESULT を返します。 次の値を指定できます。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 メソッドがプロファイラーオブジェクトを初期化できない場合、スクリプトエンジンに通知するためにエラー HRESULT が返されます。 この場合、スクリプトエンジンは直接[IActiveScriptProfilerCallback:: Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)を呼び出し、パラメーターに HRESULT を渡してから、profiler オブジェクトを解放する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerCallback インターフェイス](../../winscript/reference/iactivescriptprofilercallback-interface.md)
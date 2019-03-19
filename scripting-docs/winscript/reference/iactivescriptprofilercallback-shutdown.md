---
title: IActiveScriptProfilerCallback::Shutdown |Microsoft Docs
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
ms.openlocfilehash: 091ccc30f16081fdca8f10778efec208ef5ccb16
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58154453"
---
# <a name="iactivescriptprofilercallbackshutdown"></a>IActiveScriptProfilerCallback::Shutdown
プロファイラー オブジェクトをスクリプト エンジンのプロファイリングを停止するたびに通知するために呼び出されます。 これにより、必要な場合、プロファイラーのオブジェクトでそのクリーンアップ ルーチンを呼び出すことができます。 スクリプト エンジンのシャット ダウンするとき、またはへの呼び出しに、このメソッドはスクリプト エンジンによって呼び出されますも[IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)は失敗します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Shutdown(  
    [in] HRESULT hrReason);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hrReason`  
 [in]シャット ダウンの理由です。 スクリプト エンジンのシャット ダウン場合`S_OK`が渡されます。 場合に呼び出し[IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)エラー HRESULT を返します、HRESULT が渡されます。 この値を取得する場合は、 [IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドの戻り値は、スクリプト エンジンによって無視されます。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerCallback インターフェイス](../../winscript/reference/iactivescriptprofilercallback-interface.md)
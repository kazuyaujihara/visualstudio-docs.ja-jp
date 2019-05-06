---
title: IActiveScriptProfilerCallback::OnFunctionExit |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.OnFunctionExit
apilocation:
- scrobj.dll
ms.assetid: a5d21715-2b0b-423e-8644-f04a9e7cde3d
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c84b64a12b1a6b61399f70b7209c86dd8d2a9a4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62993333"
---
# <a name="iactivescriptprofilercallbackonfunctionexit"></a>IActiveScriptProfilerCallback::OnFunctionExit
オブジェクト、スクリプト エンジン関数の実行が完了するを呼び出すことが呼び出しではありません、ドキュメント オブジェクト モデル (DOM) に、プロファイラーに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnFunctionExit(  
    [in] PROFILER_TOKEN scriptId,   
    [in] PROFILER_TOKEN functionId);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `scriptId`  
 [in]スクリプトの一部では、関数の一意の ID。 この ID は、スクリプト エンジンによって割り当てられます。  
  
 `functionId`  
 [in]関数の一意の ID。 この ID は、スクリプト エンジンによって割り当てられます。  
  
## <a name="return-value"></a>戻り値  
 このメソッドの戻り値は、スクリプト エンジンによって無視されます。  
  
## <a name="remarks"></a>Remarks  
 スクリプト エンジンの呼び出し、DOM 呼び出し[IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)の代わりに`IActiveScriptProfilerCallback::OnFunctionExit`します。 これは一意のメソッドと DOM のプロパティの数が多いためです。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)   
 [IActiveScriptProfilerCallback インターフェイス](../../winscript/reference/iactivescriptprofilercallback-interface.md)
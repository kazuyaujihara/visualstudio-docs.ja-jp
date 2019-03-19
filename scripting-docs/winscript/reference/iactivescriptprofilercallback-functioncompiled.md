---
title: IActiveScriptProfilerCallback::FunctionCompiled |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.FunctionCompiled
apilocation:
- scrobj.dll
ms.assetid: a7e9ef17-3891-4731-9d08-c37bc489be61
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a039f7a682babebdccad276adce55e69bb8e0bc
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58153722"
---
# <a name="iactivescriptprofilercallbackfunctioncompiled"></a>IActiveScriptProfilerCallback::FunctionCompiled
スクリプトをコンパイルするときに、スクリプト エンジン オブジェクトは、関数が発生しました、プロファイラーに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT FunctionCompiled(  
    [in] PROFILER_TOKEN functionId,  
    [in] PROFILER_TOKEN scriptId,  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] [string] const WCHAR *pwszFunctionNameHint,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `functionId`  
 [in]関数の一意の ID。 この ID は、スクリプト エンジンによって割り当てられます。  
  
 `scriptId`  
 [in]スクリプトの一部では、関数の一意の ID。  
  
 `pwszFunctionName`  
 [in]匿名関数に対する関数、または null の名前。  
  
 `pwszFunctionNameHint`  
 [in]関数、またはスクリプト エンジンが任意の名前を推測していない場合は null の推測される名前。  
  
 `pIDebugDocumentContext`  
 [in]使用可能な場合へのポインター、`IUnknown`プロファイラーは次のクエリを実行する必要がありますインターフェイス、 [IDebugDocumentContext インターフェイス](../../winscript/reference/idebugdocumentcontext-interface.md)ポインター。 それ以外の場合は null。  
  
## <a name="return-value"></a>戻り値  
 このメソッドの戻り値は、スクリプト エンジンによって無視されます。  
  
## <a name="remarks"></a>Remarks  
 これは、ホストでサポートされている場合にのみ、スクリプト エンジンは、ドキュメントのコンテキストを提供できます。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerCallback インターフェイス](../../winscript/reference/iactivescriptprofilercallback-interface.md)
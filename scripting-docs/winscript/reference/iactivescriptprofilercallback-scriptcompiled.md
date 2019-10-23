---
title: 'IActiveScriptProfilerCallback:: ScriptCompiled 済み |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.ScriptCompiled
apilocation:
- scrobj.dll
ms.assetid: 1bb8e9be-cbb1-4a61-b36c-805127a56ac7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f7252134fc86bfd63b74a181b18327212a1b2dc1
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571665"
---
# <a name="iactivescriptprofilercallbackscriptcompiled"></a>IActiveScriptProfilerCallback::ScriptCompiled
スクリプトエンジンによってスクリプトがコンパイルされたことをプロファイラーオブジェクトに通知します。 このメソッドは、コンパイルされるすべてのスクリプトに対して呼び出されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT ScriptCompiled(  
    [in] PROFILER_TOKEN scriptId,  
    [in] PROFILER_SCRIPT_TYPE type,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `scriptId`  
 からコンパイルされたスクリプトの一意の ID。 この ID は、スクリプトエンジンによって割り当てられます。  
  
 `type`  
 からコンパイルされたスクリプトの種類。 値は[PROFILER_SCRIPT_TYPE 列挙型](../../winscript/reference/profiler-script-type-enumeration.md)で定義されます。  
  
 `pIDebugDocumentContext`  
 から使用可能な場合は、プロファイラーが[IDebugDocumentContext インターフェイス](../../winscript/reference/idebugdocumentcontext-interface.md)ポインターを照会する必要がある `IUnknown` インターフェイスへのポインター。 それ以外の場合、null になります。  
  
## <a name="return-value"></a>戻り値  
 このメソッドの戻り値は、スクリプトエンジンによって無視されます。  
  
## <a name="remarks"></a>Remarks  
 スクリプトエンジンは、このがホストでサポートされている場合にのみドキュメントコンテキストを提供できます。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerCallback インターフェイス](../../winscript/reference/iactivescriptprofilercallback-interface.md)
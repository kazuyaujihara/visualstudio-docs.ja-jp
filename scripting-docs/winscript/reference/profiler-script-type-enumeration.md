---
title: PROFILER_SCRIPT_TYPE 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- PROFILER_SCRIPT_TYPE
apilocation:
- scrobj.dll
ms.assetid: 3ab6633a-6241-44f0-b837-14336f70c71e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ca90a566db422d75fefc44267ffe10504bb872ce
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157439"
---
# <a name="profilerscripttype-enumeration"></a>PROFILER_SCRIPT_TYPE 列挙型
スクリプトの種類を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef enum {  
    PROFILER_SCRIPT_TYPE_USER,  
    PROFILER_SCRIPT_TYPE_DYNAMIC,  
    PROFILER_SCRIPT_TYPE_NATIVE,  
    PROFILER_SCRIPT_TYPE_DOM  
} PROFILER_SCRIPT_TYPE;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|PROFILER_SCRIPT_TYPE_USER|ユーザーが記述したスクリプト コードを指定します。|  
|PROFILER_SCRIPT_TYPE_DYNAMIC|実行時に動的に生成されるスクリプト コードを指定します。|  
|PROFILER_SCRIPT_TYPE_NATIVE|ネイティブ関数とスクリプト エンジンによって定義されているオブジェクトのスクリプトの種類を指定します。|  
|PROFILER_SCRIPT_TYPE_DOM|Internet Explorer への呼び出しなどのドキュメント オブジェクト モデル (DOM) に呼び出しを指定します、`document.getElementById`メソッド。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト Profiler の定数、列挙型および構造体](../../winscript/reference/active-script-profiler-constants-enumerations-and-structures.md)   
 [IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)   
 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)   
 [IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)
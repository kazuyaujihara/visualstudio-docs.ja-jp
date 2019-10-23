---
title: 'IActiveScriptProfilerControl:: StartProfiling |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.StartProfiling
apilocation:
- scrobj.dll
ms.assetid: 56a7b3b7-8c21-43d0-9d8b-53bbc19fabb9
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cfc59dd43ac3eed433f92af2cdd0aefe40392c4a
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571573"
---
# <a name="iactivescriptprofilercontrolstartprofiling"></a>IActiveScriptProfilerControl::StartProfiling
スクリプトエンジンでのプロファイリングを開始します。 スクリプトエンジンは、 [CoCreateInstance](https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)を呼び出すことによって、プロファイラーオブジェクトのインスタンスを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT StartProfiling(  
    [in] REFCLSID clsidProfilerObject,  
    [in] DWORD dwEventMask,  
    [in] DWORD dwContext);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `clsidProfilerObject`  
 から作成されるプロファイラーオブジェクトのクラス識別子 (CLSID)。  
  
 `dwEventMask`  
 からイベントの種類を指定する4バイトビットマスク。 ビットは[PROFILER_EVENT_MASK 列挙型](../../winscript/reference/profiler-event-mask-enumeration.md)で定義されます。  
  
 `dwContext`  
 からプロファイラーオブジェクトに渡される4バイトの値。  
  
## <a name="return-value"></a>戻り値  
 HRESULT を返します。 次の値を指定できます。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|メソッドが成功しました。|  
|`ACTIVPROF_E_PROFILER_PRESENT`|プロファイルは既に有効になっています。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerControl インターフェイス](../../winscript/reference/iactivescriptprofilercontrol-interface.md)
---
title: 'IActiveScriptProfilerControl:: SetProfilerEventMask |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.SetProfilerEventMask
apilocation:
- scrobj.dll
ms.assetid: 207e192f-e12e-4fcb-b4d8-eaee50ecb86e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a4162cf2e5325bfb41bce9c3a47a52b1b36d74f2
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571579"
---
# <a name="iactivescriptprofilercontrolsetprofilereventmask"></a>IActiveScriptProfilerControl::SetProfilerEventMask
スクリプトエンジンが発生させるイベントの種類を指定する4バイトのビットマスクを設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetProfilerEventMask(  
    [in] DWORD dwEventMask);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwEventMask`  
 からイベントの種類を指定する4バイトビットマスク。 ビットは[PROFILER_EVENT_MASK 列挙型](../../winscript/reference/profiler-event-mask-enumeration.md)で定義されます。  
  
## <a name="return-value"></a>戻り値  
 HRESULT を返します。 次の値を指定できます。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|メソッドが成功しました。|  
|`ACTIVPROF_E_PROFILER_ABSENT`|プロファイルが有効になっていません。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerControl インターフェイス](../../winscript/reference/iactivescriptprofilercontrol-interface.md)
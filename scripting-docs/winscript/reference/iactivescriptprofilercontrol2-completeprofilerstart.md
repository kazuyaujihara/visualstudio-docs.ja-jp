---
title: IActiveScriptProfilerControl2::CompleteProfilerStart |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerControl2::CompleteProfilerStart
ms.assetid: e14d94a2-39d3-40a1-84d9-6300fbe2b339
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 36a1f5d6a1401e2860b65a29c8e383627e83c6be
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144447"
---
# <a name="iactivescriptprofilercontrol2completeprofilerstart"></a>IActiveScriptProfilerControl2::CompleteProfilerStart
該当するすべてのスクリプト エンジンでプロファイリングを開始したことをプロファイラーに通知します。 このメソッドを使用する場合、完全な呼び出し履歴を取得できます[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]プロファイリングを開始するときに実行します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CompleteProfilerStart();  
```  
  
#### <a name="parameters"></a>パラメーター  
 メソッドには、すべてのパラメーターは取りません。  
  
## <a name="return-value"></a>戻り値  
 HRESULT を返します。 次の値を指定できます。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_FAIL`|プロファイリングを開始できません。|  
|`S_FALSE`|スクリプトが実行されていない場合、プロファイリングが開始されました。|  
|`ACTIVPROF_E_PROFILER_ABSENT`|プロファイルが有効になっていません。 コールバックが設定されていません。|  
|`E_OUTOFMEMORY`|呼び出し履歴は、メモリ不足の状態のため取得できません。|  
  
## <a name="remarks"></a>Remarks  
 呼び出す`IActiveScriptProfilerControl2::CompleteProfilerStart`により既に呼び出し履歴内の関数のイベントが送信されます。 このメソッドは、プロファイルの現在のタブ上にある任意のスクリプティング エンジンの開始後に呼び出す必要があります。メソッドは、任意のスクリプティング エンジンに対して呼び出すことができます。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md)   
 [IActiveScriptProfilerControl2 インターフェイス](../../winscript/reference/iactivescriptprofilercontrol2-interface.md)
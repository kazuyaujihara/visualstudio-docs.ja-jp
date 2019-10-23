---
title: 'IActiveScriptSite:: OnScriptTerminate |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnScriptTerminate
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnScriptTerminate
ms.assetid: 3301ddf4-5929-404c-81d3-1a720e589008
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a715b39b07df4183d4ec542a1dd82b4229d1f41e
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570210"
---
# <a name="iactivescriptsiteonscriptterminate"></a>IActiveScriptSite::OnScriptTerminate
スクリプトの実行が完了したことをホストに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnScriptTerminate(  
    VARIANT *pvarResult,   // address of script results  
    EXCEPINFO *pexcepinfo  // address of structure with exception information  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pvarResult`  
 からスクリプトの結果を含む変数のアドレス。スクリプトによって結果が生成されなかった場合は `NULL`。  
  
 `pexcepinfo`  
 からスクリプトの終了時に生成された例外情報を含む `EXCEPINFO` 構造体のアドレス。または、例外が生成されなかった場合は `NULL`。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `S_OK` を返します。  
  
## <a name="remarks"></a>Remarks  
 スクリプトエンジンは、SCRIPTSTATE_INITIALIZED フラグが設定されている[IActiveScriptSite:: OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)メソッドの呼び出しが完了する前に、このメソッドを呼び出します。 このメソッドを使用して、完了ステータスと結果をホストに返すことができます。 ホストからのシンクイベントに基づく多くのスクリプト言語には、ホストで定義されている有効期間があることに注意してください。 この場合、このメソッドを呼び出すことはできません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
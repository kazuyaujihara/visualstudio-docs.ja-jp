---
title: IActiveScriptSite::OnEnterScript |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnEnterScript
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnEnterScript
ms.assetid: 1ed9178c-fe80-41c4-b74d-23b85f9cddbf
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5505b30bbfd4e1cbc33022d38d7b7170ffd37dd3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992689"
---
# <a name="iactivescriptsiteonenterscript"></a>IActiveScriptSite::OnEnterScript
スクリプト エンジンのスクリプト コードの実行が開始されたことをホストに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnEnterScript(void);  
```  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `S_OK` を返します。  
  
## <a name="remarks"></a>Remarks  
 スクリプト エンジンは、スクリプト エンジンに、エントリまたは再入するたびにこのメソッドを呼び出す必要があります。 たとえば、スクリプト オブジェクトを呼び出し、スクリプト エンジンによって処理されるイベントを発生させる場合は、スクリプト エンジン呼び出す必要があります`IActiveScriptSite::OnEnterScript`前に、イベントを実行して、呼び出す必要があります、 [IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md)メソッド、イベントを実行した後は、イベントを発生させたオブジェクトを返す前にします。 このメソッドの呼び出しを入れ子にすることができます。 このメソッドを呼び出すたびに対応する呼び出しを必要と`IActiveScriptSite::OnLeaveScript`します。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
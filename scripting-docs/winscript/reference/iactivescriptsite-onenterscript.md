---
title: 'IActiveScriptSite:: OnEnterScript |Microsoft Docs'
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
ms.openlocfilehash: 26e4f221014d90478bbbc7bb5771276706c764c0
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570367"
---
# <a name="iactivescriptsiteonenterscript"></a>IActiveScriptSite::OnEnterScript
スクリプトエンジンがスクリプトコードの実行を開始したことをホストに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnEnterScript(void);  
```  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `S_OK` を返します。  
  
## <a name="remarks"></a>Remarks  
 スクリプトエンジンは、すべてのエントリに対してこのメソッドを呼び出すか、スクリプトエンジンに再入力する必要があります。 たとえば、スクリプトエンジンによって処理されるイベントを発生させるオブジェクトをスクリプトが呼び出す場合、スクリプトエンジンは、イベントを実行する前に `IActiveScriptSite::OnEnterScript` を呼び出す必要があります。また、イベントの実行後に[IActiveScriptSite:: OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md)メソッドを呼び出す必要があります。ただし、その前に、イベントを発生させたオブジェクトに戻ります。 このメソッドの呼び出しは入れ子にすることができます。 このメソッドを呼び出すたびに、`IActiveScriptSite::OnLeaveScript` への対応する呼び出しが必要になります。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
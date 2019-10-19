---
title: 'IActiveScriptSite:: OnLeaveScript |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnLeaveScript
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnLeaveScript
ms.assetid: 79af0e22-fbe3-4fae-8a5f-7af8b857678d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e9d872948fea14998f9c6f8140467d6e4c83d056
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570318"
---
# <a name="iactivescriptsiteonleavescript"></a>IActiveScriptSite::OnLeaveScript
スクリプトエンジンがスクリプトコードの実行から返されたことをホストに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnLeaveScript(void);  
```  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `S_OK` を返します。  
  
## <a name="remarks"></a>Remarks  
 スクリプトエンジンは、スクリプトエンジンに入った呼び出し元アプリケーションに制御を返す前に、このメソッドを呼び出す必要があります。 たとえば、スクリプトエンジンによって処理されるイベントを発生させるオブジェクトをスクリプトが呼び出す場合、スクリプトエンジンは、イベントを実行する前に[IActiveScriptSite:: OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md)メソッドを呼び出す必要があります。また、イベントの実行後に `IActiveScriptSite::OnLeaveScript` を呼び出す必要があります。イベントを発生させたオブジェクトに戻る前。 このメソッドの呼び出しは入れ子にすることができます。 @No__t_0 を呼び出すたびに、このメソッドへの対応する呼び出しが必要になります。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
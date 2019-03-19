---
title: IActiveScriptSite::OnLeaveScript |Microsoft Docs
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
ms.openlocfilehash: da39058a8f069c4799835108372d11849d86444e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160746"
---
# <a name="iactivescriptsiteonleavescript"></a>IActiveScriptSite::OnLeaveScript
スクリプト コードを実行してから、スクリプト エンジンが返されることをホストに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnLeaveScript(void);  
```  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `S_OK` を返します。  
  
## <a name="remarks"></a>Remarks  
 スクリプト エンジンでは、スクリプト エンジンが入力された呼び出し元アプリケーションに制御を戻す前に、このメソッドを呼び出す必要があります。 たとえば、スクリプト オブジェクトを呼び出し、スクリプト エンジンによって処理されるイベントを発生させる場合は、スクリプト エンジン呼び出す必要があります、 [IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md)メソッド、イベントを実行する前にを呼び出す必要がありますと`IActiveScriptSite::OnLeaveScript`後イベントのイベントを発生させたオブジェクトを返す前に実行します。 このメソッドの呼び出しを入れ子にすることができます。 すべての呼び出しに`IActiveScriptSite::OnEnterScript`このメソッドに対応する呼び出しが必要です。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
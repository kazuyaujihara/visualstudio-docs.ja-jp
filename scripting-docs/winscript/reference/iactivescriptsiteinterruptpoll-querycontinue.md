---
title: IActiveScriptSiteInterruptPoll::QueryContinue | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteInterruptPoll.QueryContinue
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteInterruptPoll::QueryContinue
ms.assetid: 41ac3807-f8b4-4a0e-bcc6-556bc89f3904
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63ce45c0973d65d240136d7b42aef0c078b00c9a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58154310"
---
# <a name="iactivescriptsiteinterruptpollquerycontinue"></a>IActiveScriptSiteInterruptPoll::QueryContinue
により、ホストは、スクリプトが終了することを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT QueryContinue();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドには、パラメーターはありません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|呼び出しが成功したし、ホストが継続して実行するスクリプトを許可します。|  
|`S_FALSE`|成功した呼び出しと、スクリプトを終了するホストの要求。|  
  
## <a name="remarks"></a>Remarks  
 しない限り、ホストされているスクリプトを終了する必要がありますの戻り値、`QueryContinue`メソッドは`S_OK`します。 戻り値`S_FALSE`ホスト明示的に要求していること、スクリプトが終了することを示します。  
  
 マルチ スレッドのホストを使用して、可能性があります、`IActiveScript::InterruptScriptThread`スクリプトを終了するメソッド。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSiteInterruptPoll インターフェイス](../../winscript/reference/iactivescriptsiteinterruptpoll-interface.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)
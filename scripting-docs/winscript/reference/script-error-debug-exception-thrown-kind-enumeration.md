---
title: SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: b3aa4966-e110-4b30-b368-1281a9740dbd
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9dae0161e3337411a56e316e04cf467a1f05e6a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155720"
---
# <a name="scripterrordebugexceptionthrownkind-enumeration"></a>SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND 列挙型
スローされた例外の種類を示します。 この列挙体を使って、 [IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md)メソッド。  
  
> [!IMPORTANT]
>  これらの定数は、PDM Version 11.0 以降によって実装されます。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|[値]|説明|  
|------------|-----------|-----------------|  
|ETK_FIRST_CHANCE|0x00000000|例外は初回例外です。|  
|ETK_USER_UNHANDLED|0x00000001|例外は、ユーザー コードでハンドルされません。|  
|ETK_UNHANDLED|0x00000002|例外は、コードでハンドルされません。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptErrorDebug110 インターフェイス](../../winscript/reference/iactivescripterrordebug110-interface.md)
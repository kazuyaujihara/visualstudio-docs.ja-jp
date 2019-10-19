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
ms.openlocfilehash: 8eb089efbf608b488465809f997ffc82fc2c2e3c
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574410"
---
# <a name="script_error_debug_exception_thrown_kind-enumeration"></a>SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND 列挙型
スローされた例外の種類を示します。 この列挙体は、 [IActiveScriptErrorDebug110:: GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md)メソッドによって使用されます。  
  
> [!IMPORTANT]
> これらの定数は、PDM Version 11.0 以降によって実装されます。 activdbg100.h にあります。  
  
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
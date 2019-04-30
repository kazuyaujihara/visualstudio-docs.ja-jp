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
ms.openlocfilehash: 3be6989195eacdd4d70bd13790d55e4f6cfc769d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443650"
---
# <a name="scripterrordebugexceptionthrownkind-enumeration"></a>SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND 列挙型
スローされた例外の種類を示します。 この列挙体を使って、 [IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md)メソッド。  
  
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
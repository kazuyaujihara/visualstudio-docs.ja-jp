---
title: 'IActiveScriptWinRTErrorDebug:: GetCapabilitySid |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptWinRTErrorDebug::GetCapabilitySid
ms.assetid: 469463d2-5e73-4c53-9ffd-d0ca7460aa5c
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93bf824dd4d290ca536cb609e24b5d14400a3e3b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577931"
---
# <a name="iactivescriptwinrterrordebuggetcapabilitysid"></a>IActiveScriptWinRTErrorDebug::GetCapabilitySid
使用可能な場合は Windows ランタイムエラーの機能 SID を返します。  
  
> [!IMPORTANT]
> [IActiveScriptWinRTErrorDebug インターフェイス](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)は、PDM version 11.0 以降で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetCapabilitySid([out] BSTR * capabilitySid);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `capabilitySid`  
 エラーの機能 SID。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptWinRTErrorDebug インターフェイス](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)
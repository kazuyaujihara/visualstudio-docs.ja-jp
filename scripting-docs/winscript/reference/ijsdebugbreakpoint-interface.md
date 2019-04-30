---
title: IJsDebugBreakPoint インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 791c8488-21e7-46be-b1b4-fe74117cf200
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14823baeb999ad24aabef9b2b55b59a7b5d08c71
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62583107"
---
# <a name="ijsdebugbreakpoint-interface"></a>IJsDebugBreakPoint インターフェイス
ブレークポイントを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
IJsDebugBreakPoint : public IUnknown;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IJsDebugBreakPoint::Delete メソッド](../../winscript/reference/ijsdebugbreakpoint-delete-method.md)|ブレークポイントを削除します。|  
|[IJsDebugBreakPoint::Disable メソッド](../../winscript/reference/ijsdebugbreakpoint-disable-method.md)|ブレークポイントを無効にします。|  
|[IJsDebugBreakPoint::Enable メソッド](../../winscript/reference/ijsdebugbreakpoint-enable-method.md)|ブレークポイントを有効にします。|  
|[IJsDebugBreakPoint::GetDocumentPosition メソッド](../../winscript/reference/ijsdebugbreakpoint-getdocumentposition-method.md)|ブレークポイントが関連付けられたステートメントの位置を返します。|  
|[IJsDebugBreakPoint::IsEnabled メソッド](../../winscript/reference/ijsdebugbreakpoint-isenabled-method.md)|ブレークポイントが有効かどうかを指定します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** jscript9diag.h です  
  
## <a name="see-also"></a>関連項目  
 [Windows スクリプト インターフェイスのリファレンス](../../winscript/reference/windows-script-interfaces-reference.md)
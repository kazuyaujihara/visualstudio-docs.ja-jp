---
title: IJsDebugBreakPoint::D メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJSDebugBreakPoint.Disable
apilocation:
- jscript9diag.dll
ms.assetid: f6f2889c-c001-4ee5-8e3f-4f36235e4fad
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51e4be2abc8b5a507e091b330de1779cfb14b57e
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577735"
---
# <a name="ijsdebugbreakpointdisable-method"></a>IJsDebugBreakPoint::Disable メソッド
ブレークポイントを無効にします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Disable(void);  
```  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>Remarks  
 削除されたブレークポイントで呼び出された場合は E_UNEXPECTED を返します。 既に無効になっているブレークポイントで呼び出された場合は S_FALSE を返します。  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugBreakPoint インターフェイス](../../winscript/reference/ijsdebugbreakpoint-interface.md)
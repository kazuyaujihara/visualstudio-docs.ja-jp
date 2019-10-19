---
title: 'IDebugApplication:: FCanJitDebug |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.FCanJitDebug
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::FCanJitDebug
ms.assetid: d7ddac65-4864-411f-bf66-34a46c03f239
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d68240ffd86935e9936642c09d5131f70b46e9ab
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576877"
---
# <a name="idebugapplicationfcanjitdebug"></a>IDebugApplication::FCanJitDebug
Just-in-time (JIT) デバッガーが登録されているかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp
BOOL FCanJitDebug();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドはパラメーターを受け取りません。  
  
## <a name="return-value"></a>戻り値  
 メソッドが成功し、JIT デバッガーが登録されると、メソッドは `TRUE` を返します。 それ以外の場合は、 `FALSE`を返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、JIT デバッガーが登録されているかどうかを判断します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplication インターフェイス](../../winscript/reference/idebugapplication-interface.md)
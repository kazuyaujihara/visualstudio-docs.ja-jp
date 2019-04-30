---
title: IActiveScriptError::GetExceptionInfo |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptError.GetExceptionInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptError_GetExceptionInfo
ms.assetid: 528416cc-8468-4ad7-a6c2-fa1daf6ecf33
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 71e8f787e6837e6fa41c7b3cd831448b5d20a95e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63009572"
---
# <a name="iactivescripterrorgetexceptioninfo"></a>IActiveScriptError::GetExceptionInfo
スクリプト エンジンでスクリプトの実行中に発生したエラーに関する情報を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetExceptionInfo(  
    EXCEPINFO *pexcepinfo  // structure for exception information  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pexcepinfo`  
 [out]アドレス、`EXCEPINFO`エラー情報を受け取る構造体。  
  
## <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、または`E_FAIL`場合は、エラーが発生しました。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)
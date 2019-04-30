---
title: IActiveScriptError::GetSourcePosition |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptError.GetSourcePosition
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptError_GetSourcePosition
ms.assetid: ae9b26b1-82a7-4645-9686-3261d8248664
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4446235a9584bc45fad84b6f92ecc02592e554f3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63009625"
---
# <a name="iactivescripterrorgetsourceposition"></a>IActiveScriptError::GetSourcePosition
スクリプト エンジンでスクリプトの実行中にエラーが発生したソース コード内の場所を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetSourcePosition(  
    DWORD *pdwSourceContext,  // context cookie  
    ULONG *pulLineNumber,     // line number of error  
    LONG *pichCharPosition    // character position of error  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pdwSourceContext`  
 [out]コンテキストを識別するクッキーを受け取る変数のアドレス。 このパラメーターの解釈は、ホスト アプリケーションによって異なります。  
  
 `pulLineNumber`  
 [out]エラーが発生したソース ファイル内の行番号を受け取る変数のアドレス。  
  
 `pichCharPosition`  
 [out]エラーが発生した行の文字位置を受け取る変数のアドレス。  
  
## <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、または`E_FAIL`場合は、場所を取得できませんでした。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)
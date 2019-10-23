---
title: 'IActiveScriptError:: GetSourcePosition |Microsoft Docs'
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
ms.openlocfilehash: 76ed307f988a3e5bf77ff978c466eda6e5dfee18
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576893"
---
# <a name="iactivescripterrorgetsourceposition"></a>IActiveScriptError::GetSourcePosition
スクリプトエンジンでスクリプトを実行中にエラーが発生したソースコード内の場所を取得します。  
  
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
 入出力コンテキストを識別するクッキーを受け取る変数のアドレス。 このパラメーターの解釈は、ホストアプリケーションによって異なります。  
  
 `pulLineNumber`  
 入出力エラーが発生したソースファイル内の行番号を受け取る変数のアドレス。  
  
 `pichCharPosition`  
 入出力エラーが発生した行内の文字位置を受け取る変数のアドレス。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は `S_OK` を返し、場所が取得されなかった場合は `E_FAIL` します。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)
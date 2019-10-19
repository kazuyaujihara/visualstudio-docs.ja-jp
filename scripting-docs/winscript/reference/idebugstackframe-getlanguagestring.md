---
title: 'IDebugStackFrame:: Get言語 String |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugStackFrame.GetLanguageString
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugStackFrame::GetLanguageString
ms.assetid: 561d6306-f214-422f-abc9-b502cbfbe208
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 83abb038cd8bc018d84cd0c5ddd2a413f8a02248
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576754"
---
# <a name="idebugstackframegetlanguagestring"></a>IDebugStackFrame::GetLanguageString
言語の短いテキストまたは長い説明を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetLanguageString(  
   BOOL   fLong,  
   BSTR*  pbstrLanguage  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fLong`  
 からフラグ。 `TRUE` は長い説明を返し、`FALSE` は簡単な説明を返します。  
  
 `pbstrLanguage`  
 入出力言語の説明。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 通常、`fLong` が `FALSE` 場合、このメソッドは、スタックフレームに関連付けられている言語の名前のみを提供します。 @No__t_0 が `TRUE` 場合、このメソッドは完全な製品の説明を提供することがあります。  
  
## <a name="see-also"></a>関連項目  
 [IDebugStackFrame インターフェイス](../../winscript/reference/idebugstackframe-interface.md)
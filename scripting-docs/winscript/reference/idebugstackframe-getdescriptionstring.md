---
title: 'IDebugStackFrame:: GetDescriptionString |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugStackFrame.GetDescriptionString
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugStackFrame::GetDescriptionString
ms.assetid: a2ddc069-c440-4dee-98dc-ab7c78773b94
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7eb29574d240a02073721046cec65bdf483b3eb0
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576746"
---
# <a name="idebugstackframegetdescriptionstring"></a>IDebugStackFrame::GetDescriptionString
スタックフレームの短いテキストまたは長い説明を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDescriptionString(  
   BOOL   fLong,  
   BSTR*  pbstrDescription  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fLong`  
 からフラグ。 `TRUE` は長い説明を返し、`FALSE` は簡単な説明を返します。  
  
 `pbstrDescription`  
 入出力スタックフレームの説明。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 通常、`fLong` が `FALSE` 場合、このメソッドはスタックフレームに関連付けられている関数の名前のみを提供します。 @No__t_0 が `TRUE` 場合、このメソッドは、関数のパラメーターやその他の関連情報を提供することもあります。  
  
## <a name="see-also"></a>関連項目  
 [IDebugStackFrame インターフェイス](../../winscript/reference/idebugstackframe-interface.md)
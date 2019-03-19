---
title: Ijsdebugbreakpoint::getdocumentposition メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJSDebugBreakPoint.GetDocumentPosition
apilocation:
- jscript9diag.dll
ms.assetid: 886df8ba-a59a-48a7-87f2-3b669e71528f
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 146eb26c887cd24d1eb7af858535fcecac62b41d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149329"
---
# <a name="ijsdebugbreakpointgetdocumentposition-method"></a>IJsDebugBreakPoint::GetDocumentPosition メソッド
ブレークポイントが関連付けられたステートメントの位置を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDocumentPosition(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pDocumentId`  
 [出力] ソース ドキュメントの一意の ID (IDebugDocumentText へのポインター)。  
  
 `pCharacterOffset`  
 [出力] スクリプトの先頭からの 0 から始まるオフセット。  
  
 `pStatementCharCount`  
 [出力] *pCharacterOffset から始まる現在のステートメントの長さ (文字数)。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** jscript9diag.h です  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugBreakPoint インターフェイス](../../winscript/reference/ijsdebugbreakpoint-interface.md)
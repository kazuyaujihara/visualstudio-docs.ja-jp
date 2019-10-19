---
title: 'IJsDebugFrame:: GetReturnAddress メソッド |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.GetReturnAddress
apilocation:
- jscript9diag.dll
ms.assetid: 7f10c1d6-d7b9-402e-9020-04cded37f9d3
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 802355bdef386ceb252e776f8c6e798df18c9253
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577361"
---
# <a name="ijsdebugframegetreturnaddress-method"></a>IJsDebugFrame::GetReturnAddress メソッド
フレームの "先頭" (GetStackRange を参照) でプッシュされるリターン アドレスを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetReturnAddress(  
   UINT64 *pReturnAddress  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pReturnAddress`  
 [出力] リターン アドレス。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugFrame インターフェイス](../../winscript/reference/ijsdebugframe-interface.md)
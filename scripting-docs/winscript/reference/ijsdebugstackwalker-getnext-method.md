---
title: 'IJsDebugStackWalker:: GetNext メソッド |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugStackWalker.GetNext
apilocation:
- jscript9diag.dll
ms.assetid: 0b124768-50d3-4a69-876c-1aa337839a4e
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa667402b46a3404c31dfe26307a5893c68ffcc0
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574032"
---
# <a name="ijsdebugstackwalkergetnext-method"></a>IJsDebugStackWalker::GetNext メソッド
次のフレームを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetNext(  
   IJsDebugFrame **ppFrame  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppFrame`  
 [出力] スタック フレームを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>Remarks  
 列挙するスタック フレームがなくなると E_JsDEBUG_OUTSIDE_OF_VM を返します。  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugStackWalker インターフェイス](../../winscript/reference/ijsdebugstackwalker-interface.md)
---
title: 'IJsDebugFrame:: GetStackRange メソッド |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.GetStackRange
apilocation:
- jscript9diag.dll
ms.assetid: a6d1d8be-efc0-442d-9756-1959c8f102bd
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1ac3cbee9d16296632477f4128ec36370ab0d4a
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574042"
---
# <a name="ijsdebugframegetstackrange-method"></a>IJsDebugFrame::GetStackRange メソッド
論理的な JavaScript スタック フレームの絶対アドレス範囲を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetStackRange(  
   UINT64 *pStart,  
   UINT64 *pEnd  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pStart`  
 [出力] フレームの末尾のスタック ポインター。  
  
 `pEnd`  
 [出力] フレームの先頭のスタック ポインター。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、複数のランタイムから収集されインタリーブ化されたスタック トレースを統合する場合に役立ちます。 開始スタックポインターには、複数の物理マシンスタックフレーム (解釈された JavaScript ランタイムフレーム用) を含めることができます。 スタックが上位アドレスから低アドレスに大きくなると > 終了します。  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugFrame インターフェイス](../../winscript/reference/ijsdebugframe-interface.md)
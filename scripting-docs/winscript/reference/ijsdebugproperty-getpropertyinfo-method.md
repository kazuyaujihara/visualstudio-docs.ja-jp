---
title: 'IJsDebugProperty:: GetPropertyInfo メソッド |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugProperty.GetPropertyInfo
apilocation:
- jscript9diag.dll
ms.assetid: ab9d6e0b-0448-4f21-b0b0-1738867587d2
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cf56189c42ef5c696441426191a6850d03ade416
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577319"
---
# <a name="ijsdebugpropertygetpropertyinfo-method"></a>IJsDebugProperty::GetPropertyInfo メソッド
このオブジェクトの情報を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetPropertyInfo(  
   UINT nRadix,  
   JsDebugPropertyInfo *pPropertyInfo  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nRadix`  
 [入力] 使用する基数。  
  
 `pPropertyInfo`  
 [出力] オブジェクトに関する情報。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugProperty インターフェイス](../../winscript/reference/ijsdebugproperty-interface.md)
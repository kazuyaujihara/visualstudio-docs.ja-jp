---
title: Ijsdebugproperty::getpropertyinfo メソッド |Microsoft Docs
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
ms.openlocfilehash: 0769bf137845655c3fe0bf87bf0a57c6c6cbc09e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977772"
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** jscript9diag.h です  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugProperty インターフェイス](../../winscript/reference/ijsdebugproperty-interface.md)
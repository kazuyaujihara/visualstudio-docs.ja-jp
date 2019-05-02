---
title: Ijsenumdebugproperty::next メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsEnumDebugProperty.Next
apilocation:
- jscript9diag.dll
ms.assetid: 9fad1893-483a-440c-88c1-469494212300
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3ec6a1dded8c24de06a5746261a19b6609a97ada
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977540"
---
# <a name="ijsenumdebugpropertynext-method"></a>IJsEnumDebugProperty::Next メソッド
このオブジェクトのプロパティを読み取ります。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Next(  
   ULONG count,  
   IJsDebugProperty **ppDebugProperty,  
   ULONG *pActualCount  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `count`  
 [入力] 読み取るプロパティの数。  
  
 `ppDebugProperty`  
 [出力] プロパティ ブラウザーを表すオブジェクト。  
  
 `pActualCount`  
 [出力] オブジェクトのプロパティの実際の数。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** jscript9diag.h です  
  
## <a name="see-also"></a>関連項目  
 [IJsEnumDebugProperty インターフェイス](../../winscript/reference/ijsenumdebugproperty-interface.md)
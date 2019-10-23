---
title: 'IJsEnumDebugProperty:: Next メソッド |Microsoft Docs'
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
ms.openlocfilehash: 48c4506d783093395b2d88b7a71d56e3a89d24e8
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573983"
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
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsEnumDebugProperty インターフェイス](../../winscript/reference/ijsenumdebugproperty-interface.md)
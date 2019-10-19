---
title: 'IPerPropertyBrowsing2:: Setpre Value |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.SetPredefinedValue
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::SetPredefinedValue
ms.assetid: 3aff5300-c5a4-4d9b-9d47-a75b64014ac4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a823a04082b7e19b2c1bc475c1070cc501789e8
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576241"
---
# <a name="iperpropertybrowsing2setpredefinedvalue"></a>IPerPropertyBrowsing2::SetPredefinedValue
@No__t_0 によって指定されたプロパティの値を設定します。 定義済みの値は、トークンによって識別され `dwCookie.`  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetPredefinedValue(  
   DISPID  dispid,  
   DWORD  dwCookie  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dispid`  
 から定義済みの値が設定されているプロパティのディスパッチ識別子。  
  
 `dwCookie`  
 から設定する値を識別するトークン。  
  
## <a name="return-value"></a>戻り値  
 は、有効な `HRESULT` (通常は `S_OK`) を返します。  
  
## <a name="see-also"></a>関連項目  
 [IPerPropertyBrowsing2 インターフェイス 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)
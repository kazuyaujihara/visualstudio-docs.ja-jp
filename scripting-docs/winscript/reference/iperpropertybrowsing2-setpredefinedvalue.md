---
title: IPerPropertyBrowsing2::SetPredefinedValue |Microsoft Docs
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
ms.openlocfilehash: 4d35e087cc057608666e104681d65fa8009f8167
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58146579"
---
# <a name="iperpropertybrowsing2setpredefinedvalue"></a>IPerPropertyBrowsing2::SetPredefinedValue
指定されたプロパティの値を設定`dispID`します。 定義済みの値は、トークンで識別されます。 `dwCookie.`  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetPredefinedValue(  
   DISPID  dispid,  
   DWORD  dwCookie  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dispid`  
 [in]定義済みの値の設定対象のプロパティのディスパッチ識別子。  
  
 `dwCookie`  
 [in]設定する値を識別するトークンです。  
  
## <a name="return-value"></a>戻り値  
 有効な返します`HRESULT`、通常`S_OK`します。  
  
## <a name="see-also"></a>関連項目  
 [IPerPropertyBrowsing2 インターフェイス 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)
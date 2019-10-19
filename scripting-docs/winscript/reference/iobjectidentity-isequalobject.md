---
title: 'IObjectIdentity:: IsEqualObject |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IObjectIdentity.IsEqualObject
apilocation:
- scrobj.dll
helpviewer_keywords:
- IsEqualObject method
ms.assetid: 78c5c5c2-d299-4036-986c-7c1d87cbe7cd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 636dfa07b1fc94dfec2273220aa4101f5cd085b1
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571464"
---
# <a name="iobjectidentityisequalobject"></a>IObjectIdentity::IsEqualObject
オブジェクトが現在のオブジェクトと等しいかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT IsEqualObject(  
  IUnknown*punk  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `punk`  
 から現在のオブジェクトと比較するオブジェクトのアドレス。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|オブジェクトが等しい。|  
|`S_FALSE`|オブジェクトが等しくありません。|  
  
## <a name="remarks"></a>Remarks  
 @No__t_0 メソッドの実装は、オブジェクトが同一である場合にのみ `S_OK` を返す必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IObjectIdentity インターフェイス](../../winscript/reference/iobjectidentity-interface.md)
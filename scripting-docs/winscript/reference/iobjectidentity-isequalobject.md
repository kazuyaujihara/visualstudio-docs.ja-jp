---
title: IObjectIdentity::IsEqualObject |Microsoft Docs
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
ms.openlocfilehash: c215a15a1239f07272079783366a1617c3a626e2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62944889"
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
 [in]現在のオブジェクトと比較するオブジェクトのアドレス。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|オブジェクトが等しいです。|  
|`S_FALSE`|オブジェクトが等しくないです。|  
  
## <a name="remarks"></a>Remarks  
 実装、`IsEqualObject`メソッドが返す`S_OK`オブジェクトが同じ場合にのみです。  
  
## <a name="see-also"></a>関連項目  
 [IObjectIdentity インターフェイス](../../winscript/reference/iobjectidentity-interface.md)
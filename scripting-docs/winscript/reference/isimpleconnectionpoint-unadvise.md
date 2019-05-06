---
title: ISimpleConnectionPoint::Unadvise |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISimpleConnectionPoint.Unadvise
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::Unadvise
ms.assetid: eae06a58-ed42-4839-aad4-14420b15343f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 189c07c10e93df9a61218b6a94a0b317999676d2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63001491"
---
# <a name="isimpleconnectionpointunadvise"></a>ISimpleConnectionPoint::Unadvise
以前に確立したアドバイザリ コネクションを終了`ISimpleConnectionPoint::Advise`します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Unadvise(  
   DWORD  dwCookie  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 [in]終了から返されるへの接続トークン`ISimpleConnectionPoint::Advise`します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 アドバイザリ コネクションを終了すると、接続ポイントの呼び出し、`Release`中に、接続の保存されたポインターをメソッド、`ISimpleConnectionPoint::Advise`メソッド。 呼び出す直前に、`AddRef`中で実行された、`ISimpleConnectionPoint::Advise`接続ポイントが、アドバイズ シンクを呼び出したときに`QueryInterface`します。  
  
## <a name="see-also"></a>関連項目  
 [ISimpleConnectionPoint インターフェイス](../../winscript/reference/isimpleconnectionpoint-interface.md)
---
title: ISimpleConnectionPoint::Advise |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISimpleConnectionPoint.Advise
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::Advise
ms.assetid: 59ded60d-b938-4110-aca3-e69ba234ca9a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 98db9c92f682808ce8ecc9f6aa382a2eb2bd8495
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786263"
---
# <a name="isimpleconnectionpointadvise"></a>ISimpleConnectionPoint::Advise
単純な接続ポイント オブジェクトとクライアントのシンクの間の接続を確立します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Advise(  
   IDispatch*  pdisp,  
   DWORD*      pdwCookie  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pdisp`  
 [in]ポインター、`IDispatch`クライアント上のインターフェイスのシンクをお勧めします。 クライアントのシンクは、単純な接続ポイントからの発信呼び出しを受信します。  
  
 `pdwCookie`  
 [out]この接続を一意に識別する返されたトークンへのポインター。 呼び出し元このトークンを使用して後でに渡すことによって、接続の削除、`ISimpleConnectionPoint::Unadvise`メソッド。 接続が正常に確立されませんが、この値は 0 です。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、単純な接続ポイント オブジェクトとクライアントのシンクの間の接続を確立します。  
  
## <a name="see-also"></a>関連項目  
 [ISimpleConnectionPoint インターフェイス](../../winscript/reference/isimpleconnectionpoint-interface.md)   
 [ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)
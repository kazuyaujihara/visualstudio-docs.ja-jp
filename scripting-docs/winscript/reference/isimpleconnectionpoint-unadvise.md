---
title: 'ISimpleConnectionPoint:: アドバイズ |Microsoft Docs'
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
ms.openlocfilehash: e00c172fd33eb0ccf27aaf28e0e2f692c1a353ab
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571752"
---
# <a name="isimpleconnectionpointunadvise"></a>ISimpleConnectionPoint::Unadvise
以前に `ISimpleConnectionPoint::Advise` によって確立されたアドバイザリコネクションを終了します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Unadvise(  
   DWORD  dwCookie  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 から@No__t_0 から返された、終了する接続のトークン。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 アドバイザリコネクションが終了すると、接続ポイントは、`ISimpleConnectionPoint::Advise` メソッド中に接続用に保存されたポインターの `Release` メソッドを呼び出します。 この呼び出しは、コネクションポイントがアドバイザリシンクの `QueryInterface` を呼び出すときに、`ISimpleConnectionPoint::Advise` 中に実行された `AddRef` を反転させます。  
  
## <a name="see-also"></a>関連項目  
 [ISimpleConnectionPoint インターフェイス](../../winscript/reference/isimpleconnectionpoint-interface.md)
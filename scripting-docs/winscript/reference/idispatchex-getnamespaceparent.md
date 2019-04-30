---
title: IDispatchEx::GetNameSpaceParent |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetNameSpaceParent
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetNameSpaceParent method
ms.assetid: 0b077d39-2fd6-4390-8cd5-128d9b8dc90c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1abe2a880e12d6a4a3c1dfda32d30722525858f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63000822"
---
# <a name="idispatchexgetnamespaceparent"></a>IDispatchEx::GetNameSpaceParent
名前空間の親オブジェクトのインターフェイスを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetNameSpaceParent(  
   IUnknown **ppunk  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppunk`  
 アドレス、`IUnknown`名前空間の親のインターフェイスを受け取るインターフェイス ポインター。  
  
## <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、または OLE 定義のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDispatchEx インターフェイス](../../winscript/reference/idispatchex-interface.md)
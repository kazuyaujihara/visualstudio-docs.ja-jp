---
title: 'IPerPropertyBrowsing2:: MapPropertyToPage |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.MapPropertyToPage
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::MapPropertyToPage
ms.assetid: e6418a8e-500b-42e1-9b5a-52e6f7567f99
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e9e3f821d9e02be567f970d8db1c238ee5cebd29
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577127"
---
# <a name="iperpropertybrowsing2mappropertytopage"></a>IPerPropertyBrowsing2::MapPropertyToPage
このプロパティを編集するために使用できるプロパティページの CLSID を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT MapPropertyToPage(  
   DISPID  dispid,  
   CLSID*  pClsidPropPage  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dispid`  
 から目的のプロパティのディスパッチ識別子。  
  
 `pClsidPropPage`  
 入出力プロパティに関連付けられているプロパティページを識別する CLSID へのポインター。 このメソッドが失敗した場合、* `pClsidPropPage` は CLSID_NULL に設定されます。  
  
## <a name="return-value"></a>戻り値  
 は、有効な `HRESULT` (通常は `S_OK`) を返します。  
  
## <a name="see-also"></a>関連項目  
 [IPerPropertyBrowsing2 インターフェイス 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)
---
title: 'IDebugProperty:: GetExtendedInfo |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.GetExtendedInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::GetExtendedInfo
ms.assetid: a989ade5-16d5-4ee6-8d8a-8dcbfad24034
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 130d11c8ed6bb21210d129bb9aace779db3bd54b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72562395"
---
# <a name="idebugpropertygetextendedinfo"></a>IDebugProperty::GetExtendedInfo
プロパティの拡張情報を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetExtendedInfo (  
   ULONG  cInfos,  
   GUID*  rgguidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cInfos`  
 から拡張情報オブジェクトの数。  
  
 `rgguidExtendedInfo`  
 から拡張情報の複数の項目を同時に取得できるように、`GUID`s の配列が渡されます。  
  
 `pExtendedInfo`  
 入出力拡張プロパティ情報を取得するために使用できる `VARIANT`s の配列を返します。  
  
## <a name="return-value"></a>戻り値  
 は、有効な `HRESULT` (通常は `S_OK`) を返します。  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスは、このオブジェクトの拡張情報を取得します。 API は、`IDebugProperty::GetPropertyInfo`) の使用によって取得されることがない情報を取得する目的でのみ存在します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty インターフェイス](../../winscript/reference/idebugproperty-interface.md)
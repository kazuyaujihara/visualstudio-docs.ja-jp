---
title: IDebugProperty::GetExtendedInfo |Microsoft Docs
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
ms.openlocfilehash: 707474f786a8f88c0e08d887f2c2b09c8aaedc8e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144863"
---
# <a name="idebugpropertygetextendedinfo"></a>IDebugProperty::GetExtendedInfo
拡張プロパティの情報を取得します。  
  
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
 [in]拡張情報オブジェクトの数。  
  
 `rgguidExtendedInfo`  
 [in]配列の`GUID`拡張情報の複数の項目を同時に取得できるように、s が渡されます。  
  
 `pExtendedInfo`  
 [out]配列を返します`VARIANT`s 拡張プロパティの情報を取得するために使用できます。  
  
## <a name="return-value"></a>戻り値  
 有効な返します`HRESULT`、通常`S_OK`します。  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスは、このオブジェクトの情報を拡張を取得します。 使用して取得するのには適していません情報の取得のためだけに API が存在する`IDebugProperty::GetPropertyInfo`)。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty インターフェイス](../../winscript/reference/idebugproperty-interface.md)
---
title: 'IEnumDebugExtendedPropertyInfo:: Clone |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExtendedPropertyInfo.Clone
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugExtendedPropertyInfo::Clone
ms.assetid: dd645cf6-bfb3-486c-829e-bb91a6639665
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d11aa307342fbb6029f3bc2aed6b652417f4f52d
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72568908"
---
# <a name="ienumdebugextendedpropertyinfoclone"></a>IEnumDebugExtendedPropertyInfo::Clone
現在の列挙子と同じ列挙状態を含む列挙子を作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Clone (  
   IEnumDebugExtendedPropertyInfo** ppEnum  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 入出力複製された `IEnumDebugExtendedPropertyInfo` インターフェイスを返します。  
  
## <a name="return-value"></a>戻り値  
 は、有効な `HRESULT` (通常は `S_OK`) を返します。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugExtendedPropertyInfo インターフェイス](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)
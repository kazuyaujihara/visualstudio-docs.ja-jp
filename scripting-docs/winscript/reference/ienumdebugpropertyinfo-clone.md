---
title: 'IEnumDebugPropertyInfo:: Clone |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugPropertyInfo.Clone
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugPropertyInfo::Clone
ms.assetid: ba6bdfdb-4c12-475c-bafc-efa6c109d7ee
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e5b355d6302d846a8599b697aa9ad0159662cba
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574227"
---
# <a name="ienumdebugpropertyinfoclone"></a>IEnumDebugPropertyInfo::Clone
現在の列挙子と同じ列挙状態を含む列挙子を作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Clone (  
   IEnumDebugPropertyInfo** ppEnum  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 入出力複製された `IEnumDebugPropertyInfo` インターフェイスを返します。  
  
## <a name="return-value"></a>戻り値  
 は、有効な `HRESULT` (通常は `S_OK`) を返します。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugPropertyInfo インターフェイス](../../winscript/reference/ienumdebugpropertyinfo-interface.md)
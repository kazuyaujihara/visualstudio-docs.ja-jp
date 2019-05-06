---
title: IEnumDebugExtendedPropertyInfo::Skip |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExtendedPropertyInfo.Skip
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugExtendedPropertyInfo::Skip
ms.assetid: a0b4a9fc-e122-482b-9384-b83c460b61fe
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 87913f15f8799be0ad3f6616eeea53a8a627e3d0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963456"
---
# <a name="ienumdebugextendedpropertyinfoskip"></a>IEnumDebugExtendedPropertyInfo::Skip
指定した数のスキップ`ExtendedDebugPropertyInfo`列挙体シーケンス内の構造体。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Skip(  
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]数`ExtendedDebugPropertyInfo`をスキップする列挙体シーケンス内の構造体。  
  
## <a name="return-value"></a>戻り値  
 有効な返します`HRESULT`、通常`S_OK`します。 返します`S_FALSE`場合は、列挙体の末尾に、現在の要素のポインターを設定および`celt`列挙子の左の要素の数より大きい。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugExtendedPropertyInfo インターフェイス](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)   
 [ExtendedDebugPropertyInfo 構造体](../../winscript/reference/extendeddebugpropertyinfo-structure.md)
---
title: IDebugProperty::GetParent |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.GetParent
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::GetParent
ms.assetid: 673d625b-acca-45c4-88f4-b72275042f8f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2aeac5e23ec38aa79e5ff5057847429ac97dbb23
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152211"
---
# <a name="idebugpropertygetparent"></a>IDebugProperty::GetParent
プロパティの親プロパティを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetParent (  
   IDebugProperty** ppParent  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppParent`  
 [out]返します、`IDebugProperty`プロパティの親を表すインターフェイスです。  
  
## <a name="return-value"></a>戻り値  
 有効な返します`HRESULT`、通常`S_OK`します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty インターフェイス](../../winscript/reference/idebugproperty-interface.md)
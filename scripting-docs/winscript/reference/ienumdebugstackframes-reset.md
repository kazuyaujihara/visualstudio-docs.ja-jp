---
title: IEnumDebugStackFrames::Reset |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugStackFrames.Reset
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugStackFrames::Reset
ms.assetid: 57be2683-5346-4464-bdf5-6fd45b56253a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76cb09ef9456f0dccf3bd034914c9988dd0ff187
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963339"
---
# <a name="ienumdebugstackframesreset"></a>IEnumDebugStackFrames::Reset
先頭に、列挙体シーケンスをリセットします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Reset();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドには、パラメーターはありません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、先頭に、列挙体シーケンスをリセットします。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugStackFrames インターフェイス](../../winscript/reference/ienumdebugstackframes-interface.md)
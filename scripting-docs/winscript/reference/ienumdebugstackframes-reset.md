---
title: 'IEnumDebugStackFrames:: Reset |Microsoft Docs'
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
ms.openlocfilehash: ddd97d60d40eaa15a5ed3e17cc87a0d9ffb197cf
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574862"
---
# <a name="ienumdebugstackframesreset"></a>IEnumDebugStackFrames::Reset
列挙シーケンスを先頭にリセットします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Reset();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドはパラメーターを受け取りません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、列挙体のシーケンスを先頭にリセットします。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugStackFrames インターフェイス](../../winscript/reference/ienumdebugstackframes-interface.md)
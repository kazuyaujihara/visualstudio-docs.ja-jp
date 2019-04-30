---
title: IEnumDebugCodeContexts::Next |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugCodeContexts.Next
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugCodeContexts::Next
ms.assetid: 844cc353-ae0b-45e1-84a6-32b0bb67f57f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 86a0e3f58d9f4a13295f689551f6f2a20b287854
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62807401"
---
# <a name="ienumdebugcodecontextsnext"></a>IEnumDebugCodeContexts::Next
指定した列挙体シーケンス内のセグメント数を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Next(  
   ULONG                celt,  
   IDebugCodeContext**  pscc,  
   ULONG*               pceltFetched  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]取得するセグメントの数。  
  
 `pscc`  
 [out]配列を返します`IDebugCodeContext`を取得するセグメントを表すインターフェイス。  
  
 `pceltFetched`  
 [out]列挙子によってフェッチされるセグメントの実際の数。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、指定した列挙体シーケンス内のセグメント数を取得します。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugCodeContexts インターフェイス](../../winscript/reference/ienumdebugcodecontexts-interface.md)
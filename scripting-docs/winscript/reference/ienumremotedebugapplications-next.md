---
title: IEnumRemoteDebugApplications::Next |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumRemoteDebugApplications.Next
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumRemoteDebugApplications::Next
ms.assetid: 33f6c620-6dd3-4057-b982-b88a7a1f02b4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b14874891e739fc95b877e41e76559a1ab0060a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963238"
---
# <a name="ienumremotedebugapplicationsnext"></a>IEnumRemoteDebugApplications::Next
`Next`メソッドは、指定した列挙体シーケンス内のセグメント数を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Next(  
   ULONG                      celt,  
   IRemoteDebugApplication**  ppda,  
   ULONG*                     pceltFetched  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]取得するセグメントの数。  
  
 `ppda`  
 [out]配列を返します`IRemoteDebugApplication`を取得するセグメントを表すインターフェイス。  
  
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
 [IEnumRemoteDebugApplications インターフェイス](../../winscript/reference/ienumremotedebugapplications-interface.md)
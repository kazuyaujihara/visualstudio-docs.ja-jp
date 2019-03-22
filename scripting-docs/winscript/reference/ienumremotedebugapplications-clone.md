---
title: IEnumRemoteDebugApplications::Clone |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumRemoteDebugApplications.Clone
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumRemoteDebugApplications::Clone
ms.assetid: 762f6dac-1be4-49ec-afda-68c1b29f7a4b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06b2eac008b0bccc3d0671e15658b5a189b5dcaa
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58158894"
---
# <a name="ienumremotedebugapplicationsclone"></a>IEnumRemoteDebugApplications::Clone
現在の列挙子と同じ状態を格納する列挙子を作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Clone(  
   IEnumRemoteDebugApplications**  ppessd  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppessd`  
 [out]列挙子の複製。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、現在の列挙子と同じ状態を格納する列挙子を作成します。  
  
## <a name="see-also"></a>関連項目  
 [IEnumRemoteDebugApplications インターフェイス](../../winscript/reference/ienumremotedebugapplications-interface.md)
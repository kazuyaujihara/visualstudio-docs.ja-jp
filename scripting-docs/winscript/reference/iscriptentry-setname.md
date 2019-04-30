---
title: IScriptEntry::SetName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetName
ms.assetid: dfa33450-87d7-4c8e-bfd8-0cc2d6542a0e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6476869a54921cfdac34e9f1ed202adef909ddf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62787602"
---
# <a name="iscriptentrysetname"></a>IScriptEntry::SetName
(関数) などの 1 つのオブジェクトを表すエントリの場合は、オブジェクトの名前を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetName(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `psz`  
 [in]新しい名前、`IScriptEntry`オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetName](../../winscript/reference/iscriptentry-getname.md)
---
title: IScriptEntry::GetName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetName
ms.assetid: 56daa288-618f-497c-a360-7d443afd478b
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d23843aa72ce5cf79f6442048b6493d17eb6ef64
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62787771"
---
# <a name="iscriptentrygetname"></a>IScriptEntry::GetName
(関数) などの 1 つのオブジェクトを表すエントリの場合は、オブジェクトの名前を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetName(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstr`  
 [out]によって表されるオブジェクトの名前、`IScriptEntry`スクリプト ブロック。 エントリが 1 つのオブジェクトを表していない場合は、NULL が返されます。  
  
 子のエントリは、1 つの関数オブジェクトを表します。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptNode::CreateChildEntry](../../winscript/reference/iscriptnode-createchildentry.md)
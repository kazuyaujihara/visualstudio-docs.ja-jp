---
title: 'IScriptEntry:: GetItemName |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetItemName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetItemName
ms.assetid: 8f2562f1-8231-4a39-ad79-074f9ec3d403
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dcd1b83fa6d22fafc2123645f1f252fa1325f7f1
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575462"
---
# <a name="iscriptentrygetitemname"></a>IScriptEntry::GetItemName
@No__t_0 オブジェクトを識別する項目名を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetItemName(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstr`  
 入出力項目名を格納しているバッファーのアドレス。 項目名は、エントリを識別するためにホストによって使用されます。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 @No__t_0 オブジェクトの場合は、 [IActiveScriptAuthor:: AddScriptlet レット](../../winscript/reference/iactivescriptauthor-addscriptlet.md)を使用して項目名を設定します。 他のインターフェイスの場合は、 [Iscriptentry:: SetItemName](../../winscript/reference/iscriptentry-setitemname.md)を使用して項目名を設定します。  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)
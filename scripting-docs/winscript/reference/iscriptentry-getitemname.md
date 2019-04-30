---
title: IScriptEntry::GetItemName |Microsoft Docs
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
ms.openlocfilehash: 9d8abc6d1264ce532adcbc59c262510a39ea7a91
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62787857"
---
# <a name="iscriptentrygetitemname"></a>IScriptEntry::GetItemName
識別する項目の名前を返します、`IScriptEntry`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetItemName(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstr`  
 [out]項目の名前を格納するバッファーのアドレス。 項目の名前は、エントリを識別するために、ホストによって使用されます。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 `IScriptScriptlet`オブジェクトを使用して、項目の名前を設定する[IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md)します。 その他のインターフェイスを使用して、項目の名前を設定する[IScriptEntry::SetItemName](../../winscript/reference/iscriptentry-setitemname.md)します。  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)
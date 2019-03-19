---
title: IScriptEntry::SetItemName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetItemName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetItemName
ms.assetid: 9551a7ec-38f8-466a-9722-09367763f380
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d25ac4977f1fca44d63767c372db169f8cb61ea6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160551"
---
# <a name="iscriptentrysetitemname"></a>IScriptEntry::SetItemName
識別する項目の名前を設定、`IScriptEntry`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetItemName(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `psz`  
 [in]項目の名前を格納するバッファーのアドレス。 項目の名前は、エントリを識別するために、ホストによって使用されます。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_FAIL`|メソッドは成功しませんでした。|  
  
## <a name="remarks"></a>Remarks  
 `IScriptEntry`オブジェクトの場合、このメソッドが戻る`S_OK`します。  
  
 `IScriptScriptlet`オブジェクト (から派生する`IScriptEntry`)、このメソッドが戻る`E_FAIL`します。 `IScriptScriptlet`オブジェクトによって、項目の名前が設定されます[IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md)変更ことはできません。  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetItemName](../../winscript/reference/iscriptentry-getitemname.md)
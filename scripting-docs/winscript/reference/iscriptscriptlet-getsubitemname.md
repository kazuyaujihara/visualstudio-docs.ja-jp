---
title: IScriptScriptlet::GetSubItemName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptScriptlet.GetSubItemName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptScriptlet::GetSubItemName
ms.assetid: 9ad963fc-9ce8-4b77-92c1-fb90d6307801
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c48517b7f9f5fab3250b8cff68ad288525145b9
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155905"
---
# <a name="iscriptscriptletgetsubitemname"></a>IScriptScriptlet::GetSubItemName
スクリプトレットのオブジェクトのホストの完全修飾名では、最後の識別子を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetSubItemName(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstr`  
 [out]スクリプトレットの名前が 1 つ以上のレベルを持つ場合は、ホストの完全修飾`pbstr`2 番目のレベルで識別子のバッファーのアドレスを返します。  
  
 スクリプトレットの名前が 1 つのレベルを持つ場合は、ホストの完全修飾`pbstr`最初のレベルで識別子のバッファーのアドレスを返します。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptScriptlet インターフェイス](../../winscript/reference/iscriptscriptlet-interface.md)
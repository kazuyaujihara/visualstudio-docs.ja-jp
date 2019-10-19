---
title: 'IScriptScriptlet レット:: GetSubItemName |Microsoft Docs'
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
ms.openlocfilehash: b36f6dd98534b8122a6814f1fd154eca7882251a
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571921"
---
# <a name="iscriptscriptletgetsubitemname"></a>IScriptScriptlet::GetSubItemName
スクリプトレットのオブジェクトホストの完全修飾名の最後の識別子を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetSubItemName(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstr`  
 入出力ホストの完全修飾されたスクリプトレット名に複数のレベルがある場合、`pbstr` は2番目のレベルで識別子のバッファーアドレスを返します。  
  
 ホストの完全修飾されたスクリプトレット名に1つのレベルがある場合、`pbstr` は、最初のレベルで識別子のバッファーアドレスを返します。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptScriptlet インターフェイス](../../winscript/reference/iscriptscriptlet-interface.md)
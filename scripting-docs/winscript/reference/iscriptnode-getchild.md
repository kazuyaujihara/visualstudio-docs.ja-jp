---
title: IScriptNode::GetChild |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetChild
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetChild
ms.assetid: 8cb3f8b0-958b-40bb-a91a-49a788661861
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78b5c84c6ed9b3de9593f0d6ff02df93a0e9ba77
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58159115"
---
# <a name="iscriptnodegetchild"></a>IScriptNode::GetChild
ノードで指定したインデックス位置にある子を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetChild(  
   ULONG              isn,  
   IScriptNode        **ppsn  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `isn`  
 [in]親の子のインデックス。  
  
 `ppsn`  
 [out]ポインターを受け取る変数のアドレス、`IScriptNode`子インスタンスのインターフェイス。  
  
 `IScriptNode` Web ページを表すオブジェクトの場合は、このパラメーターは、スクリプト ブロックを格納しているオブジェクトを返します。  
  
 `IScriptEntry`スクリプト ブロックを指定するオブジェクトの場合は、このパラメーターは、関数を指定するオブジェクトを返します。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 `IScriptEntry`関数オブジェクトを指定するオブジェクトおよび`IScriptScriptlet`オブジェクトの場合、このメソッドは、子エントリがないために失敗します。  
  
## <a name="see-also"></a>関連項目  
 [IScriptNode インターフェイス](../../winscript/reference/iscriptnode-interface.md)
---
title: 'IScriptNode:: GetChild |Microsoft Docs'
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
ms.openlocfilehash: 27ddde527be1ea4148e4166581ab2cb1a71d15f7
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573566"
---
# <a name="iscriptnodegetchild"></a>IScriptNode::GetChild
ノード内の指定したインデックス位置にある子を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetChild(  
   ULONG              isn,  
   IScriptNode        **ppsn  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `isn`  
 から親の子のインデックス。  
  
 `ppsn`  
 入出力子インスタンスの `IScriptNode` インターフェイスへのポインターを受け取る変数のアドレス。  
  
 Web ページを表す `IScriptNode` オブジェクトの場合、このパラメーターは、スクリプトブロックを含むオブジェクトを返します。  
  
 スクリプトブロックを指定する `IScriptEntry` オブジェクトの場合、このパラメーターは関数を指定するオブジェクトを返します。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 関数オブジェクトおよび `IScriptScriptlet` オブジェクトを指定する `IScriptEntry` オブジェクトの場合、子エントリがないため、このメソッドは失敗します。  
  
## <a name="see-also"></a>関連項目  
 [IScriptNode インターフェイス](../../winscript/reference/iscriptnode-interface.md)
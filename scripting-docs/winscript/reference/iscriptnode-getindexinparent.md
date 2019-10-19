---
title: 'IScriptNode:: GetIndexInParent |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetIndexInParent
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetIndexInParent
ms.assetid: 521c1ca1-2d27-4344-bf3b-d8b53132b648
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9251f65414a5ebd48ce56dae6a7dbfeec4e514e3
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575041"
---
# <a name="iscriptnodegetindexinparent"></a>IScriptNode::GetIndexInParent
親の子リスト内のオブジェクトのインデックスを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetIndexInParent(  
   ULONG              pisn,  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pisn`  
 入出力親の子リスト内のオブジェクトのインデックスを返します。  
  
 このメソッドが Web ページを表す `IScriptNode` オブジェクトによって呼び出された場合、このパラメーターは0を返します。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptNode インターフェイス](../../winscript/reference/iscriptnode-interface.md)
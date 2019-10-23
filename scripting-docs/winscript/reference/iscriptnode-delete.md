---
title: IScriptNode::D e) |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.Delete
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::Delete
ms.assetid: 6765ff80-a9a8-40a3-a669-7fcc284c87af
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c3522e5543d333443de5b1287c994bf29de51c9
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576305"
---
# <a name="iscriptnodedelete"></a>IScriptNode::Delete
このオブジェクトツリーを削除します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Delete();  
```  
  
#### <a name="parameters"></a>パラメーター  
 メソッドはパラメーターを受け取りません。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 @No__t_0 メソッドが呼び出された後、 [Iscriptnode:: Alive](../../winscript/reference/iscriptnode-alive.md)メソッドはスクリプトノードがアクティブでないことを示す必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IScriptNode インターフェイス](../../winscript/reference/iscriptnode-interface.md)
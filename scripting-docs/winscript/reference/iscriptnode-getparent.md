---
title: 'IScriptNode:: GetParent |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetParent
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetParent
ms.assetid: 0fb813f6-ab94-46b2-b0cf-ef5d1cd38ae4
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 58ef5f88f4404d57a7edad3590fba1d2614faec6
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572554"
---
# <a name="iscriptnodegetparent"></a>IScriptNode::GetParent
オブジェクトの親である `IScriptNode` オブジェクトを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetParent(  
   IScriptNode       **ppsnParent  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppsnParent`  
 入出力親インスタンスの `IScriptNode` インターフェイスへのポインターを受け取る変数のアドレス。  
  
 クラスが `IScriptEntry` または `IScriptScriptlet` を実装している場合は、`IScriptNode` オブジェクトが返されます。  
  
 クラスが (Web ページを表す) `IScriptNode` を実装している場合は、NULL が返されます。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptNode インターフェイス](../../winscript/reference/iscriptnode-interface.md)
---
title: IScriptNode::GetParent |Microsoft Docs
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
ms.openlocfilehash: 1c990b5ba5c3d03d319e0eeced282c92cfbb5281
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58151012"
---
# <a name="iscriptnodegetparent"></a>IScriptNode::GetParent
返します、`IScriptNode`オブジェクトの親であるオブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetParent(  
   IScriptNode       **ppsnParent  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppsnParent`  
 [out]ポインターを受け取る変数のアドレス、`IScriptNode`親インスタンスのインターフェイス。  
  
 クラスが実装されている場合`IScriptEntry`または`IScriptScriptlet`、`IScriptNode`オブジェクトが返されます。  
  
 クラスが実装されている場合`IScriptNode`(Web ページを表す)、NULL が返されます。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptNode インターフェイス](../../winscript/reference/iscriptnode-interface.md)
---
title: 'IDebugApplicationNode:: Attach |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNode.Attach
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationNode::Attach
ms.assetid: f4aad4ae-5bb0-4b5e-8f70-912a677f8f7a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30d4e189ec878def1cfd88517654955cd2d1aa12
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574785"
---
# <a name="idebugapplicationnodeattach"></a>IDebugApplicationNode::Attach
このアプリケーションノードを指定されたプロジェクトツリーに追加します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Attach(  
   IDebugApplicationNode*  pdanParent  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pdanParent`  
 からこのアプリケーションノードが追加されるプロジェクトツリー。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、`pdanParent` を親として使用して、このアプリケーションノードをプロジェクトツリーに追加します。 @No__t_0 が `NULL` 場合、このアプリケーションノードは最上位ノードになります。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationNode::D etach](../../winscript/reference/idebugapplicationnode-detach.md)  
 [IDebugApplicationNode インターフェイス](../../winscript/reference/idebugapplicationnode-interface.md)
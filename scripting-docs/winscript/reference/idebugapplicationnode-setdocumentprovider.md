---
title: IDebugApplicationNode::SetDocumentProvider |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNode.SetDocumentProvider
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationNode::SetDocumentProvider
ms.assetid: 7cb587ca-d84e-4b5e-9b94-e973cca55a03
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9dc81397e2ebe19ae125eba7599c97337f58d967
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58153072"
---
# <a name="idebugapplicationnodesetdocumentprovider"></a>IDebugApplicationNode::SetDocumentProvider
このアプリケーションのノードのドキュメント プロバイダーを設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetDocumentProvider(  
   IDebugDocumentProvider*  pddp  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pddp`  
 [in]このアプリケーションのノードのドキュメント プロバイダー。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、このアプリケーションのノードのドキュメント プロバイダーを設定します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationNode インターフェイス](../../winscript/reference/idebugapplicationnode-interface.md)
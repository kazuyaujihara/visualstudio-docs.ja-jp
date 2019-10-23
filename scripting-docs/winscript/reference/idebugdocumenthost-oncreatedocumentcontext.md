---
title: 'IDebugDocumentHost:: OnCreateDocumentContext |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.OnCreateDocumentContext
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::OnCreateDocumentContext
ms.assetid: 080c8604-cfd7-484e-a337-15040870e683
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3fdfa64f66288cba47dec7c498db15238e55f954
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72569112"
---
# <a name="idebugdocumenthostoncreatedocumentcontext"></a>IDebugDocumentHost::OnCreateDocumentContext
新しいドキュメントコンテキストが作成されていることをホストに通知します。また、ホストは、新しいコンテキストに対して、必要に応じて不明な制御を返すことができます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnCreateDocumentContext(  
   IUnknown**  ppunkOuter  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppunkOuter`  
 入出力新しいコンテキストを制御するオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_NOTIMPL`|ホストが制御オブジェクトを提供していません。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドを使用すると、ホストはヘルパーによって提供されるドキュメントコンテキストに新しい機能を追加できます。 このメソッドは、 **E_NOTIMPL**または null 外部オブジェクトを返す場合があります。この場合、呼び出し元はコンテキストの作成を担当します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHost インターフェイス](../../winscript/reference/idebugdocumenthost-interface.md)
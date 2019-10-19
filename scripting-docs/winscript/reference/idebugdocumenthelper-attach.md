---
title: 'IDebugDocumentHelper:: Attach |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.Attach
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::Attach
ms.assetid: 834f23a9-716d-44df-b23c-d1bf6da60e79
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3400a5bf6cd3e4a9726fdf4b2f20bbf43b9fc989
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577031"
---
# <a name="idebugdocumenthelperattach"></a>IDebugDocumentHelper::Attach
このドキュメントをドキュメントツリーに追加します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Attach(  
   IDebugDocumentHelper*  pddhParent  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pddhParent`  
 からこのドキュメントが追加されるドキュメントツリー。 NULL を指定できます。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、`pddhParent` を親として使用して、ドキュメントツリーにこのドキュメントを追加します。 @No__t_0 が `NULL` 場合、このドキュメントは最上位のドキュメントになります。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHelper::D etach](../../winscript/reference/idebugdocumenthelper-detach.md)  
 [IDebugDocumentHelper インターフェイス](../../winscript/reference/idebugdocumenthelper-interface.md)
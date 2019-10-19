---
title: 'IDebugDocumentInfo:: GetDocumentClassId |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentInfo.GetDocumentClassId
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentInfo::GetDocumentClassId
ms.assetid: 3b858794-2c0c-42ba-b98c-cd820ebace20
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 996e6d751807bba1e1a74cbb7e579db25193c32b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72569087"
---
# <a name="idebugdocumentinfogetdocumentclassid"></a>IDebugDocumentInfo::GetDocumentClassId
ドキュメントの種類を識別する `CLSID` を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDocumentClassId(  
   CLSID*  pclsidDocument  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pclsidDocument`  
 入出力ドキュメントの種類を識別する `CLSID`。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、デバッガー IDE がこのドキュメントのカスタムビューアーをホストできるようにします。  
  
 ドキュメントに表示可能なデータがない場合、`pclsidDocument` の戻り値は `CLSID_NULL` になります。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentInfo インターフェイス](../../winscript/reference/idebugdocumentinfo-interface.md)
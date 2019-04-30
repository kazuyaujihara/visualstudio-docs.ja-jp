---
title: IDebugDocumentContext::EnumCodeContexts |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentContext.EnumCodeContexts
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentContext::EnumCodeContexts
ms.assetid: fb0aa64e-c458-4ef1-bcd8-5cebdc972549
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ecf8b7d1ea292d0e1464825314cc92e1e903db3e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974424"
---
# <a name="idebugdocumentcontextenumcodecontexts"></a>IDebugDocumentContext::EnumCodeContexts
このドキュメントのコンテキストに関連付けられたコード コンテキストを列挙します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT EnumCodeContexts(  
   IEnumDebugCodeContexts**  ppescc  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppescc`  
 [out]このドキュメントのコンテキストに関連付けられたコード コンテキスト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 ドキュメントがインクルード ファイルまたはテンプレートでない限り、ドキュメントは通常 1 つだけのコードのコンテキストに関連付けられてです。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentContext インターフェイス](../../winscript/reference/idebugdocumentcontext-interface.md)
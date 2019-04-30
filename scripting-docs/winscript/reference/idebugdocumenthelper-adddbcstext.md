---
title: Idebugdocumenthelper::adddbcstext |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.AddDBCSText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::AddDBCSText
ms.assetid: 5e5011b2-bbb4-491b-9a11-eb2846be44aa
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d346f3877574c45aaff6dcef8ca99f699a42552
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446653"
---
# <a name="idebugdocumenthelperadddbcstext"></a>IDebugDocumentHelper::AddDBCSText
このドキュメントの最後に、DBCS 文字列を追加します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AddDBCSText(  
   LPCSTR  pszText  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszText`  
 [in]テキストを含む null で終わる文字列へのポインター。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_FAIL`|メソッドは、文字を追加できませんでした。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、生成`IDebugDocumentTextEvents`通知します。  
  
> [!NOTE]
> 後にこのメソッドが呼び出された場合`IDebugDocumentHelper::AddDeferredText`が呼び出された`E_FAIL`が返されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHelper インターフェイス](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [:Adddeferredtext](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [IDebugDocumentTextEvents インターフェイス](../../winscript/reference/idebugdocumenttextevents-interface.md)
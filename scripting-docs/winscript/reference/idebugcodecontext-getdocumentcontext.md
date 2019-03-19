---
title: IDebugCodeContext::GetDocumentContext |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugCodeContext.GetDocumentContext
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugCodeContext::GetDocumentContext
ms.assetid: 9fe17b65-3a8c-4d21-9b66-0e4ff303af72
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 48c707432ddb94fae111c971b89c8ff74f34ac21
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150778"
---
# <a name="idebugcodecontextgetdocumentcontext"></a>IDebugCodeContext::GetDocumentContext
このコードのコンテキストに関連付けられているドキュメント コンテキストを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDocumentContext(  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppsc`  
 [out]このコードのコンテキストに関連付けられているドキュメント コンテキスト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 テキスト ドキュメント、文字位置の範囲は、ステートメント全体のテキストを含める必要があります。 これにより、デバッガーを現在のソース ステートメントを強調表示の IDE です。  
  
## <a name="see-also"></a>関連項目  
 [IDebugCodeContext インターフェイス](../../winscript/reference/idebugcodecontext-interface.md)
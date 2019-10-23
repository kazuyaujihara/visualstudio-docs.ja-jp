---
title: 'IDebugCodeContext:: GetDocumentContext |Microsoft Docs'
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
ms.openlocfilehash: 9dc1cda6164375f3434ee562b540e85268fe4c68
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573226"
---
# <a name="idebugcodecontextgetdocumentcontext"></a>IDebugCodeContext::GetDocumentContext
このコードコンテキストに関連付けられているドキュメントコンテキストを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDocumentContext(  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppsc`  
 入出力このコードコンテキストに関連付けられているドキュメントコンテキスト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 テキストドキュメントの場合、文字位置の範囲には、ステートメント全体のテキストが含まれている必要があります。 これにより、デバッガー IDE で現在のソースステートメントを強調表示できるようになります。  
  
## <a name="see-also"></a>関連項目  
 [IDebugCodeContext インターフェイス](../../winscript/reference/idebugcodecontext-interface.md)
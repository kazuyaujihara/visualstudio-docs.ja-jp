---
title: IActiveScriptDebug::EnumCodeContextsOfPosition |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptDebug.EnumCodeContextsOfPosition
apilocation:
- jscript.dll
helpviewer_keywords:
- IActiveScriptDebug::EnumCodeContextsOfPosition
ms.assetid: 19f44420-bcc8-4c10-8c38-378d96044117
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c364d00941a65272b4d22cc7674a0f0e6178f099
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63009743"
---
# <a name="iactivescriptdebugenumcodecontextsofposition"></a>IActiveScriptDebug::EnumCodeContextsOfPosition
委任にスマート ホストによって使用される、`IDebugDocumentContext::EnumCodeContexts`メソッド。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT EnumCodeContextsOfPosition(  
   DWORD_PTR                 dwSourceContext,  
   ULONG                     uCharacterOffset,  
   ULONG                     uNumChars,  
   IEnumDebugCodeContexts**  ppescc  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwSourceContext`  
 [in]元のコンテキストに提供する`IActiveScriptParse::ParseScriptText`または`IActiveScriptParse::AddScriptlet`します。  
  
 `uCharacterOffset`  
 [in]スクリプトのテキストの先頭を基準としたオフセットの文字。  
  
 `uNumChars`  
 [in]このコンテキスト内の文字の数。  
  
 `ppescc`  
 [out]指定した範囲内のコードのコンテキストの列挙子。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 スマート ホストでは、このメソッドを使用して、デリゲート、`IDebugDocumentContext::EnumCodeContexts`メソッド。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptDebug インターフェイス](../../winscript/reference/iactivescriptdebug-interface.md)   
 [IDebugDocumentContext::EnumCodeContexts](../../winscript/reference/idebugdocumentcontext-enumcodecontexts.md)
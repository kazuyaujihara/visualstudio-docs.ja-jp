---
title: IDebugExpressionContext::GetLanguageInfo | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpressionContext.GetLanguageInfo
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpressionContext::GetLanguageInfo
ms.assetid: 35e25662-0b2a-4c3f-bce4-f01726bc04a8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ed5546f07a81d9c2825f3dbdc4f2bb28887948f9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946291"
---
# <a name="idebugexpressioncontextgetlanguageinfo"></a>IDebugExpressionContext::GetLanguageInfo
このコンテキストを所有している言語の名前と GUID を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetLanguageInfo(  
   BSTR*  pbstrLanguageName,  
   GUID*  pLanguageID  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrLanguageName`  
 [out]言語の名前。  
  
 `pLanguageID`  
 [out]言語の一意の id。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、このコンテキストを所有している言語の名前と GUID を返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExpressionContext インターフェイス](../../winscript/reference/idebugexpressioncontext-interface.md)
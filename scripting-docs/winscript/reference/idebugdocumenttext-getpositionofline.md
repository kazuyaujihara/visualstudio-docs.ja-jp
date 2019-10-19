---
title: 'IDebugDocumentText:: GetPositionOfLine |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentText.GetPositionOfLine
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentText::GetPositionOfLine
ms.assetid: d1e6e81b-ddec-4a7c-9b6a-d199e3debfc2
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: adf4add99ac41440e6f4daa491b72166e97b5ba5
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572103"
---
# <a name="idebugdocumenttextgetpositionofline"></a>IDebugDocumentText::GetPositionOfLine
行の最初の文字に対応する文字位置を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetPositionOfLine(  
   ULONG   cLineNumber,  
   ULONG*  pcCharacterPosition  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cLineNumber`  
 から行番号。  
  
 `pcCharacterPosition`  
 入出力@No__t_0 行の先頭にあるドキュメント内の文字位置。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、行の最初の文字に対応する文字位置を返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentText インターフェイス](../../winscript/reference/idebugdocumenttext-interface.md)
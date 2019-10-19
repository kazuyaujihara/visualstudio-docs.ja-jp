---
title: 'IDebugDocumentText:: GetLineOfPosition |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentText.GetLineOfPosition
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentText::GetLineOfPosition
ms.assetid: fe8d4802-ea16-49ca-8973-89dcaf6c915b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e8ce32e46c42ee864a88e169a79539efb8b05633
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572119"
---
# <a name="idebugdocumenttextgetlineofposition"></a>IDebugDocumentText::GetLineOfPosition
指定された文字位置に対応する行の中で、行番号と、必要に応じて文字オフセットを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetLineOfPosition(  
   ULONG   cCharacterPosition,  
   ULONG*  pcLineNumber,  
   ULONG*  pcCharacterOffsetInLine  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cCharacterPosition`  
 から文字位置の範囲の開始位置。  
  
 `pcLineNumber`  
 入出力範囲の行番号。  
  
 `pcCharacterOffsetInLine`  
 [入力、出力]行 `pcLineNumber` 内の範囲の文字オフセット。 このパラメーターが `NULL` 場合、メソッドは値を返しません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、指定された文字位置に対応する行の中で、行番号と、必要に応じて文字オフセットを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentText インターフェイス](../../winscript/reference/idebugdocumenttext-interface.md)
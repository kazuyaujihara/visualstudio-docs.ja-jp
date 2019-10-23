---
title: 'IDebugDocumentTextAuthor:: ReplaceText |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentTextAuthor.ReplaceText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentTextAuthor::ReplaceText
ms.assetid: f89304e6-5be0-45a5-947d-2c59c3c0a05e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: beca5d0ce19a38346ef9b03e39169769c90ea008
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572037"
---
# <a name="idebugdocumenttextauthorreplacetext"></a>IDebugDocumentTextAuthor::ReplaceText
ドキュメント内のテキストを置換します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT ReplaceText(  
   ULONG    cCharacterPosition,  
   ULONG    cNumToReplace,  
   OLECHAR  pcharText[]  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cCharacterPosition`  
 から置換する文字範囲の開始位置。  
  
 `cNumToReplace`  
 から置換する文字数。  
  
 `pcharText[]`  
 から古い文字を置き換える新しい文字を格納しているバッファー。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、ドキュメント内のテキストを置換します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentTextAuthor インターフェイス](../../winscript/reference/idebugdocumenttextauthor-interface.md)
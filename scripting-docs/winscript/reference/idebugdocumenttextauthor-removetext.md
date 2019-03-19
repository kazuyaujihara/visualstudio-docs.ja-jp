---
title: IDebugDocumentTextAuthor::RemoveText |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentTextAuthor.RemoveText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentTextAuthor::RemoveText
ms.assetid: 2b74d850-c0b1-4a3c-a37c-2c8d06d1ae02
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 989031a6d4b207c69d1a58b2ff99e5797a629440
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160340"
---
# <a name="idebugdocumenttextauthorremovetext"></a>IDebugDocumentTextAuthor::RemoveText
ドキュメントからテキストを削除します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT RemoveText(  
   ULONG  cCharacterPosition,  
   ULONG  cNumToRemove  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cCharacterPosition`  
 [in]削除する文字の範囲の位置を開始します。  
  
 `cNumToRemove`  
 [in]削除する文字の数。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、ドキュメントからテキストを削除します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentTextAuthor インターフェイス](../../winscript/reference/idebugdocumenttextauthor-interface.md)   
 [IDebugDocumentTextAuthor::InsertText](../../winscript/reference/idebugdocumenttextauthor-inserttext.md)
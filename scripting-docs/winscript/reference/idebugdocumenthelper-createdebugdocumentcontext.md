---
title: IDebugDocumentHelper::CreateDebugDocumentContext |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.CreateDebugDocumentContext
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::CreateDebugDocumentContext
ms.assetid: aa4ec691-9fb1-4da7-8085-b40d8a062467
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b2dddfc76f2bbc3e629b2d48febb6b582a3a779
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150687"
---
# <a name="idebugdocumenthelpercreatedebugdocumentcontext"></a>IDebugDocumentHelper::CreateDebugDocumentContext
新しいデバッグ ドキュメントのコンテキストを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CreateDebugDocumentContext(  
   ULONG                    iCharPos,  
   ULONG                    cChars,  
   IDebugDocumentContext**  ppddc  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `iCharPos`  
 [in]デバッグ ドキュメントのコンテンツの先頭の位置。  
  
 `cChars`  
 [in]コンテキスト内の文字の数。  
  
 `ppddc`  
 [out]新しいデバッグ ドキュメントのコンテキスト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、新しいデバッグ ドキュメントのコンテキストを作成するホストを使用します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHelper インターフェイス](../../winscript/reference/idebugdocumenthelper-interface.md)
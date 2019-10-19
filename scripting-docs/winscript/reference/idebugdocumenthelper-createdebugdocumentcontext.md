---
title: 'IDebugDocumentHelper:: CreateDebugDocumentContext |Microsoft Docs'
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
ms.openlocfilehash: 24a039b5c4de410e67dc2dfb2859e1f4cc8b1739
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576988"
---
# <a name="idebugdocumenthelpercreatedebugdocumentcontext"></a>IDebugDocumentHelper::CreateDebugDocumentContext
新しいデバッグドキュメントコンテキストを作成します。  
  
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
 からデバッグドキュメントの内容の開始位置。  
  
 `cChars`  
 からコンテキスト内の文字数。  
  
 `ppddc`  
 入出力新しいデバッグドキュメントコンテキスト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドを使用すると、ホストは新しいデバッグドキュメントコンテキストを作成できます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHelper インターフェイス](../../winscript/reference/idebugdocumenthelper-interface.md)
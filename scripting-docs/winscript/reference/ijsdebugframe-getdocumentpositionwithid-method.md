---
title: 'IJsDebugFrame:: GetDocumentPositionWithId メソッド |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.GetDocumentPositionWithId
apilocation:
- jscript9diag.dll
ms.assetid: 48f8eb26-8ae4-4d5c-bd94-796023b03bcb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f35f6fb84db95950fe83d571c9f5e5e7db9de1e8
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573859"
---
# <a name="ijsdebugframegetdocumentpositionwithid-method"></a>IJsDebugFrame::GetDocumentPositionWithId メソッド
ユーザー レベルのドキュメント内でのこのスタック フレームの現在の位置を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDocumentPositionWithId(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pDocumentId`  
 [出力] ソース ドキュメントの一意の ID (IDebugDocumentText へのポインター)。  
  
 `pCharacterOffset`  
 [出力] スクリプトの先頭からの 0 から始まるオフセット。  
  
 `pStatementCharCount`  
 [出力] *pCharacterOffset から始まる現在のステートメントの長さ (文字数)。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugFrame インターフェイス](../../winscript/reference/ijsdebugframe-interface.md)
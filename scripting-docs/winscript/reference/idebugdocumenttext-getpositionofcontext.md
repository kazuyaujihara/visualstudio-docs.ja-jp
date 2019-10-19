---
title: 'IDebugDocumentText:: GetPositionOfContext |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentText.GetPositionOfContext
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentText::GetPositionOfContext
ms.assetid: 90fec730-c3fb-45fb-92ef-05ecc90dca38
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: da759eb98a6cdd28066ddaa8aafe785ede337a6e
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572134"
---
# <a name="idebugdocumenttextgetpositionofcontext"></a>IDebugDocumentText::GetPositionOfContext
ドキュメントコンテキストに対応する文字位置の範囲を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetPositionOfContext(  
   IDebugDocumentContext*  psc,  
   ULONG*                  pcCharacterPosition,  
   ULONG*                  cNumChars  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `psc`  
 からドキュメントコンテキストオブジェクト。  
  
 `pcCharacterPosition`  
 入出力文字位置の範囲の開始位置。  
  
 `cNumChars`  
 入出力範囲内の文字数。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドに指定されたドキュメントコンテキストは、このドキュメントに関連付けられている必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentText インターフェイス](../../winscript/reference/idebugdocumenttext-interface.md)
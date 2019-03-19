---
title: IDebugDocumentTextEvents::onUpdateTextAttributes |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentTextEvents.onUpdateTextAttributes
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentTextEvents::onUpdateTextAttributes
ms.assetid: 24a6d409-3137-4a7a-ac24-0955c109902f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 746339cb281d4d039759f350bb5516456ce142cf
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144473"
---
# <a name="idebugdocumenttexteventsonupdatetextattributes"></a>IDebugDocumentTextEvents::onUpdateTextAttributes
基になる文字位置の範囲に関連付けられているテキストの属性が変更されたことを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT onUpdateTextAttributes(  
   ULONG  cCharacterPosition,  
   ULONG  cNumToUpdate  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cCharacterPosition`  
 [in]属性が変更された最初の文字の文字位置。  
  
 `cNumToUpdate`  
 [in]範囲の文字の数。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、基になる文字位置の範囲に関連付けられているテキストの属性が変更されたことを示します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentTextEvents インターフェイス](../../winscript/reference/idebugdocumenttextevents-interface.md)
---
title: IDebugDocumentText::GetText |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentText.GetText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentText::GetText
ms.assetid: 3c940a30-6c0f-4deb-aa4d-21a0bdef8461
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63e1fee3531272f18c85c23ea83b8ca12920bd2a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62970862"
---
# <a name="idebugdocumenttextgettext"></a>IDebugDocumentText::GetText
文字または文字位置の範囲に関連付けられている文字の属性を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetText(  
   ULONG              cCharacterPosition,  
   WCHAR*             pcharText,  
   SOURCE_TEXT_ATTR*  pstaTextAttr,  
   ULONG*             pcNumChars,  
   ULONG              cMaxChars  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cCharacterPosition`  
 [in]開始文字位置の範囲の位置。  
  
 `pcharText`  
 [入力、出力]文字のテキスト バッファー。 バッファーを保持するために十分な大きさにする必要があります`cMaxChars`文字。 このパラメーターが NULL の場合、メソッドは文字を返しません。  
  
 `pstaTextAttr`  
 [入力、出力]文字の属性のバッファー。 バッファーを保持するために十分な大きさにする必要があります`cMaxChars`文字。 このパラメーターが NULL の場合、メソッドは、属性を返しません。  
  
 `pcNumChars`  
 [入力、出力]文字/属性の数が返されます。 このパラメーターは、このメソッドを呼び出す前にゼロに設定する必要があります。  
  
 `cMaxChars`  
 [in]位置の文字範囲の文字数。 返される文字の最大数を指定します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、文字または文字位置の範囲に関連付けられている文字の属性を取得します。 文字位置の範囲は、文字位置と文字数で指定されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentText インターフェイス](../../winscript/reference/idebugdocumenttext-interface.md)   
 [SOURCE_TEXT_ATTR 列挙型](../../winscript/reference/source-text-attr-enumeration.md)
---
title: :Adddeferredtext |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.AddDeferredText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::AddDeferredText
ms.assetid: 9463cfb0-76cc-45ee-b32c-f37dce2b2e0e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1219543c438c79ad1add068262d9556dd2d7ce8
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58159336"
---
# <a name="idebugdocumenthelperadddeferredtext"></a>IDebugDocumentHelper::AddDeferredText
指定されたテキストは、使用可能な文字は提供されませんが、ヘルパーに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AddDeferredText(  
   ULONG  cChars,  
   DWORD  dwTextStartCookie  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cChars`  
 [in]追加する (Unicode) 文字の数。  
  
 `dwTextStartCookie`  
 [in]テキストの開始位置を表すホスト定義のクッキー。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_FAIL`|メソッドが失敗しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、正確な通知およびサイズの情報を生成するヘルパーを許可するときに必要になるまでを追加する文字を提供することを遅延するホストを使用します。 `dwTextStartCookie`パラメーターは、cookie、テキストの開始位置を表すホストで定義されています。 後続の呼び出し`IDebugDocumentText::GetText`この cookie を提供する必要があります。 たとえば、DBCS でテキストを表すホストで cookie 可能性がありますのバイト オフセット。  
  
 前提とする単一の呼び出し`IDebugDocumentText::GetText`複数の呼び出しから文字を取得できます`AddDeferredText`。 遅延の文字の同じ範囲にはヘルパー クラスは複数回要求可能性があります。  
  
> [!NOTE]
>  呼び出す`AddDeferredText`への呼び出しを混在させないでください`AddUnicodeText`または`AddDBCSText`します。 この場合、`E_FAIL`が返されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHelper インターフェイス](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)   
 [Idebugdocumenthelper::adddbcstext](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)
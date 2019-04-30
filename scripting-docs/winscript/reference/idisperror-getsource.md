---
title: IDispError::GetSource |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetSource
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetSource
ms.assetid: 20def54c-a67c-4102-babf-6f0704e5fc5c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8a84640f020a1ff255b8c7e5dd753752e0d310a7
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446883"
---
# <a name="idisperrorgetsource"></a>IDispError::GetSource
クラスまたはエラーが発生したアプリケーションの言語に依存するプログラム id を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetSource(  
   BSTR*  pbstrSource  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrSource`  
 [out]フォームでのプログラム id を含む文字列`progname.objectname`します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、例外が発生したクラスまたはアプリケーションの決定に使用されます。 プログラム id は、呼び出し時に指定されたロケール識別子 (LCID) によって指定された言語で返される可能性があります。  
  
> [!NOTE]
> このメソッドは実装されていません。  
  
## <a name="see-also"></a>関連項目  
 [IDispError インターフェイス](../../winscript/reference/idisperror-interface.md)
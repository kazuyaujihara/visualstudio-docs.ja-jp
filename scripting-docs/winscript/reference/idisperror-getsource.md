---
title: 'IDispError:: GetSource |Microsoft Docs'
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
ms.openlocfilehash: 07c87585a92415f0b910210a56efa47e6f91417b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573092"
---
# <a name="idisperrorgetsource"></a>IDispError::GetSource
エラーを発生させたクラスまたはアプリケーションの言語に依存したプログラム id を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetSource(  
   BSTR*  pbstrSource  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrSource`  
 入出力@No__t_0 形式のプログラム識別子を含む文字列。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、例外が発生したクラスまたはアプリケーションを特定するために使用されます。 プログラム識別子は、呼び出し時に指定されたロケール識別子 (LCID) で指定された言語で返される場合があります。  
  
> [!NOTE]
> このメソッドは実装されていません。  
  
## <a name="see-also"></a>関連項目  
 [IDispError インターフェイス](../../winscript/reference/idisperror-interface.md)
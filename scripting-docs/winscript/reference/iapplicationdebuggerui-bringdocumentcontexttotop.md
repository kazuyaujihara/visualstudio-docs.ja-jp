---
title: IApplicationDebuggerUI::BringDocumentContextToTop |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebuggerUI.BringDocumentContextToTop
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebuggerUI::BringDocumentContextToTop
ms.assetid: 7844217d-658b-42af-8d10-2714f4eded20
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 596f9357a8553bf6c39140a6948d8ae3085c3210
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58147680"
---
# <a name="iapplicationdebuggeruibringdocumentcontexttotop"></a>IApplicationDebuggerUI::BringDocumentContextToTop
デバッガーのユーザー インターフェイスの上部に特定のドキュメント コンテキストを含むウィンドウを表示し、コンテキストにウィンドウをスクロールします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT BringDocumentContextToTop(  
   IDebugDocumentContext*  pddc  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pddc`  
 [in]デバッガー ユーザー インターフェイスの先頭に配置するドキュメントのコンテキスト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_INVALIDARG`|指定されたコンテキスト`pddc`は認識されていません。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、デバッガーのユーザー インターフェイスの上部に特定のドキュメント コンテキストを含むウィンドウを表示し、コンテキストにウィンドウをスクロールします。  
  
## <a name="see-also"></a>関連項目  
 [IApplicationDebuggerUI インターフェイス](../../winscript/reference/iapplicationdebuggerui-interface.md)
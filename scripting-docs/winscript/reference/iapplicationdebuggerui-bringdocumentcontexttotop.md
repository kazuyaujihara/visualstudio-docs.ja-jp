---
title: 'Iapplicationデバッガ Ui:: BringDocumentContextToTop |Microsoft Docs'
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
ms.openlocfilehash: 8648a4377e901908df20cdb5f413ee73ede5c1a6
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577811"
---
# <a name="iapplicationdebuggeruibringdocumentcontexttotop"></a>IApplicationDebuggerUI::BringDocumentContextToTop
指定されたドキュメントコンテキストを含むウィンドウをデバッガーのユーザーインターフェイスの上部に移動し、ウィンドウをコンテキストにスクロールします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT BringDocumentContextToTop(  
   IDebugDocumentContext*  pddc  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pddc`  
 からデバッガーのユーザーインターフェイスの上部に移動するドキュメントコンテキスト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_INVALIDARG`|@No__t_0 によって指定されたコンテキストが不明です。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、指定されたドキュメントコンテキストを含むウィンドウをデバッガーのユーザーインターフェイスの上部に移動し、ウィンドウをコンテキストにスクロールします。  
  
## <a name="see-also"></a>関連項目  
 [IApplicationDebuggerUI インターフェイス](../../winscript/reference/iapplicationdebuggerui-interface.md)
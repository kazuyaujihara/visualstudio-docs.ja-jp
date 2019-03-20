---
title: IApplicationDebuggerUI::BringDocumentToTop |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebuggerUI.BringDocumentToTop
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebuggerUI::BringDocumentToTop
ms.assetid: ef5fe1e7-4381-4409-a0d7-58f993abe84e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a8a88b44f609113670259492eb82491b16004d29
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58148244"
---
# <a name="iapplicationdebuggeruibringdocumenttotop"></a>IApplicationDebuggerUI::BringDocumentToTop
デバッガーで最上位に指定されたデバッグ ドキュメントを含むウィンドウにユーザー インターフェイスを表示します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT BringDocumentToTop(  
   IDebugDocumentText*  pddt  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pddt`  
 [in]デバッガー ユーザー インターフェイスの先頭に配置するドキュメントをデバッグします。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_INVALIDARG`|ドキュメントが不明です。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、ユーザー インターフェイスをデバッガーで最上位に指定されたデバッグ ドキュメントを含むウィンドウに表示します。  
  
## <a name="see-also"></a>関連項目  
 [IApplicationDebuggerUI インターフェイス](../../winscript/reference/iapplicationdebuggerui-interface.md)
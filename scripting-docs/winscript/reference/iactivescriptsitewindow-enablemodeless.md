---
title: 'IActiveScriptSiteWindow:: EnableModeless |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteWindow.EnableModeless
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteWindow_EnableModeless
ms.assetid: 83fe4f62-8e97-4f03-bc6f-d90aa888657d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 756bda6209b6209ff14f6d67fef18faaed0b5618
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574137"
---
# <a name="iactivescriptsitewindowenablemodeless"></a>IActiveScriptSiteWindow::EnableModeless
ホストがメインウィンドウとモードレスダイアログボックスを有効または無効にします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT EnableModeless(  
    BOOL fEnable  // enable flag  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fEnable`  
 から@No__t_0 の場合、メインウィンドウとモードレスダイアログを有効にするか、`FALSE` すると無効にするかを示すフラグ。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は `S_OK` を返し、エラーが発生した場合は `E_FAIL` します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、`IOleInPlaceFrame::EnableModeless` メソッドと同じです。  
  
 このメソッドの呼び出しは入れ子にすることができます。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSiteWindow](../../winscript/reference/iactivescriptsitewindow.md)
---
title: 'IActiveScriptSiteWindow:: GetWindow |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteWindow.GetWindow
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteWindow_GetWindow
ms.assetid: 6284e38c-9dfb-4d69-903d-f243f78c0331
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8263db447c7692ec7b0982127d63b4bea588a4b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574355"
---
# <a name="iactivescriptsitewindowgetwindow"></a>IActiveScriptSiteWindow::GetWindow
スクリプトエンジンに表示する必要があるポップアップウィンドウの所有者として機能できるウィンドウへのハンドルを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetWindow(  
    HWND *phwnd  // address of variable for window handle  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `phwnd`  
 入出力ウィンドウハンドルを受け取る変数のアドレス。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は `S_OK` を返し、エラーが発生した場合は `E_FAIL` します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、`IOleWindow::GetWindow` メソッドに似ています。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSiteWindow](../../winscript/reference/iactivescriptsitewindow.md)
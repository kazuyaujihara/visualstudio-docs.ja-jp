---
title: 'IActiveScriptSite:: OnScriptError |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnScriptError
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnScriptError
ms.assetid: 5c9c85cc-21ad-4232-be83-a24cc7570108
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9f0078b53515a881d7f2ac1475cf5565fa22a025
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570272"
---
# <a name="iactivescriptsiteonscripterror"></a>IActiveScriptSite::OnScriptError
エンジンがスクリプトを実行している間に実行エラーが発生したことをホストに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnScriptError(  
    IActiveScriptError *pase  // address of error interface  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pase`  
 からエラーオブジェクトの[IActiveScriptError](../../winscript/reference/iactivescripterror.md)インターフェイスのアドレス。 ホストは、このインターフェイスを使用して、実行エラーに関する情報を取得できます。  
  
## <a name="return-value"></a>戻り値  
 エラーが正しく処理された場合は `S_OK` を返します。それ以外の場合は、OLE 定義エラーコードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
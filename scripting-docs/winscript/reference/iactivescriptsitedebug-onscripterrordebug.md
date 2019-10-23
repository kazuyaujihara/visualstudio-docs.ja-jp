---
title: 'IActiveScriptSiteDebug:: OnScriptErrorDebug |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.OnScriptErrorDebug
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::OnScriptErrorDebug
ms.assetid: 87f201da-36eb-49a2-b000-e1e1e8c4cdb7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 894767b3dae9db54e8bc438a82b27195308a4342
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572203"
---
# <a name="iactivescriptsitedebugonscripterrordebug"></a>IActiveScriptSiteDebug::OnScriptErrorDebug
スマートホストが実行時エラーの処理方法を決定できるようにします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnScriptErrorDebug(  
   IActiveScriptErrorDebug*  pErrorDebug,  
   BOOL*                     pfEnterDebugger,  
   BOOL*                     pfCallOnScriptErrorWhenContinuing  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pErrorDebug`  
 から発生したランタイムエラー  
  
 `pfEnterDebugger`  
 入出力JIT デバッグを実行するためにエラーをデバッガーに渡すかどうかを示すフラグです。  
  
 `pfCallOnScriptErrorWhenContinuing`  
 入出力ユーザーがデバッグなしで続行することを決定した場合に `IActiveScriptSite::OnScriptError` を呼び出すかどうかを示すフラグ。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 使用できる値は次のとおりです。ただし、次の表の値には制限されません。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 スマートホストは、このメソッドを使用して、実行時エラーの処理方法を決定できます。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSiteDebug インターフェイス](../../winscript/reference/iactivescriptsitedebug-interface.md)
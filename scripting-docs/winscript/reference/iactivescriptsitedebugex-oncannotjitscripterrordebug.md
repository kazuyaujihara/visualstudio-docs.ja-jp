---
title: 'IActiveScriptSiteDebugEx:: OnCanNotJITScriptErrorDebug |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebugEx.OnCanNotJITScriptErrorDebug
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug
ms.assetid: 83f81476-bf12-47f2-897d-1d37d21137d4
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7358d2b372f0801b8c45816e1fc36018b37799b2
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572183"
---
# <a name="iactivescriptsitedebugexoncannotjitscripterrordebug"></a>IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug
プロセスデバッグマネージャーがジャストインタイムスクリプトデバッガーを見つけられない場合に、スクリプトの実行時エラーをホストに通知します。  
  
 ホストにデバッガーを実装するには、 [IActiveScriptSiteDebug:: OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md)を処理する必要があります。 ホストは、ユーザーの操作に基づいて、デバッガーをアタッチしてを返すか、OnScriptErrorDebug `pfEnterDebugger` パラメーターでデバッガーの開始を返すことができます。 また、プロセスデバッグマネージャーで解釈できる外部デバッガーがない場合でも、ランタイムエラーに関する通知を取得するには、このインターフェイスを実装する必要があります。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OnCanNotJITScriptErrorDebug(  
   IActiveScriptErrorDebug*  pErrorDebug  
   BOOL *pfCallOnScriptErrorWhenContinuing  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pErrorDebug`  
 から発生したランタイムエラー。  
  
 `pfCallOnScriptErrorWhenContinuingt`  
 入出力ユーザーがデバッグなしで続行することを決定した場合に[IActiveScriptSiteDebug:: OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md)を呼び出すかどうか。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 通知を取得するには、このインターフェイスも実装する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSiteDebugEx インターフェイス](../../winscript/reference/iactivescriptsitedebugex-interface.md)
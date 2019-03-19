---
title: IDebugApplication::HandleRuntimeError |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.HandleRuntimeError
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::HandleRuntimeError
ms.assetid: f8f3bbaf-09e5-4d01-8a35-f380bc7ff8ed
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a457ba0dcc6fb7f8a95a982b6dabd93f9d0207e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150102"
---
# <a name="idebugapplicationhandleruntimeerror"></a>IDebugApplication::HandleRuntimeError
現在のスレッドをブロックして、デバッガー IDE にエラーの通知を送信します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT HandleRuntimeError(  
   IActiveScriptErrorDebug*  pErrorDebug,  
   IActiveScriptSite*        pScriptSite,  
   BREAKRESUMEACTION*        pbra,  
   ERRORRESUMEACTION*        perra,  
   BOOL*                     pfCallOnScriptError  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pErrorDebug`  
 [in]このエラーが発生しました。  
  
 `pScriptSite`  
 [in]スレッドのスクリプト サイトです。  
  
 `pbra`  
 [out]デバッガーは、アプリケーションを再開したときに実行するアクション。  
  
 `perra`  
 [out]エラーがある場合、デバッガーは、アプリケーションを再開したときに実行するアクション。  
  
 `pfCallOnScriptError`  
 [out]これはフラグ`TRUE`場合は、エンジンを呼び出す必要があります、`IActiveScriptSite::OnScriptError`メソッド。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 言語エンジンは、実行時エラーが発生したスレッドのコンテキストでこのメソッドを呼び出します。 このメソッドは、現在のスレッドをブロックして、IDE のデバッガーに送信されるエラー通知を送信します。 デバッガー IDE、アプリケーションの再開時、このメソッドは、実行するアクションを返します。  
  
> [!NOTE]
>  実行時エラーの中にスタック フレームを列挙または式を評価すると、このようなタスクを実行するスレッドによって、言語エンジンを呼び出すことができます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplication インターフェイス](../../winscript/reference/idebugapplication-interface.md)   
 [IActiveScriptErrorDebug インターフェイス](../../winscript/reference/iactivescripterrordebug-interface.md)   
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)   
 [BREAKRESUMEACTION 列挙型](../../winscript/reference/breakresumeaction-enumeration.md)   
 [ERRORRESUMEACTION 列挙型](../../winscript/reference/errorresumeaction-enumeration.md)
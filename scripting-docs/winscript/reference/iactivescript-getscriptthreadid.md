---
title: 'IActiveScript:: GetScriptThreadID |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptThreadID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptThreadID
ms.assetid: 2595d76e-30b5-429f-88b4-1d026645dd9b
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a0fb1eebfcb6ed100056289fab6bce662f86a7b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575705"
---
# <a name="iactivescriptgetscriptthreadid"></a>IActiveScript::GetScriptThreadID
指定した Win32 スレッドに関連付けられているスレッドのスクリプトエンジン定義の識別子を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetScriptThreadID(  
    DWORD dwWin32ThreadID,       // Win32 thread identifier.  
    SCRIPTTHREADID *pstidThread  // Receives scripting thread. identifier  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwWin32ThreadID` ,  
 から現在のプロセスで実行されている Win32 スレッドのスレッド識別子。 現在実行中のスレッドのスレッド識別子を取得するには、 [IActiveScript:: GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md)関数を使用します。  
  
 `pstidThread` ,  
 入出力指定した Win32 スレッドに関連付けられているスクリプトスレッド識別子を受け取る変数のアドレス。 この識別子の解釈は、スクリプトエンジンに残されていますが、Windows スレッド識別子のコピーである場合もあります。 Win32 スレッドが終了した場合、この識別子は割り当てが解除され、その後別のスレッドに割り当てられる可能性があることに注意してください。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_UNEXPECTED`|呼び出しは想定されていませんでした (たとえば、スクリプトエンジンがまだ読み込まれていないか初期化されていないため)。そのため失敗しました。|  
  
## <a name="remarks"></a>Remarks  
 取得した識別子は、後続の呼び出しで[IActiveScript:: InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)メソッドなどのスレッド実行制御メソッドをスクリプト化するために使用できます。  
  
 このメソッドは非ベースのスレッドから呼び出すことができます。その結果、非ベースのコールアウトがオブジェクトをホストするか、 [IActiveScript:: InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)インターフェイスになりません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)
---
title: 'IActiveScript:: GetCurrentScriptThreadID |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetCurrentScriptThreadID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetCurrentScriptThreadID
ms.assetid: b09e8b48-4209-480e-8b71-e99ee9ae2e17
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dedb16e0c007ed05370fb54835f84f00784c1ae4
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575775"
---
# <a name="iactivescriptgetcurrentscriptthreadid"></a>IActiveScript::GetCurrentScriptThreadID
現在実行中のスレッドのスクリプトエンジンで定義された識別子を取得します。 この識別子は、後続の呼び出しで[IActiveScript:: InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)メソッドなどのスレッド実行制御メソッドをスクリプト化するために使用できます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetCurrentScriptThreadID(  
    SCRIPTTHREADID *pstidThread  // receives scripting thread identifier  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstidThread`  
 入出力現在のスレッドに関連付けられているスクリプトスレッド識別子を受け取る変数のアドレス。 この識別子の解釈は、スクリプトエンジンに残されていますが、Windows スレッド識別子のコピーである場合もあります。 Win32 スレッドが終了すると、この識別子は割り当てが解除され、その後別のスレッドに割り当てることができます。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は `S_OK` を返します。無効なポインターが指定された場合は `E_POINTER` を返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは非ベースのスレッドから呼び出すことができます。この場合、非ベースのコールアウトによってオブジェクトをホストするか、 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)インターフェイスを使用することはできません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)
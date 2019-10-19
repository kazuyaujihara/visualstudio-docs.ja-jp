---
title: 'IActiveScript:: InterruptScriptThread |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.InterruptScriptThread
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_InterruptScriptThread
ms.assetid: 2304d035-6d39-4811-acd3-8a9640fdbef6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a436f973df05b945c0939f3a593640f567774277
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577266"
---
# <a name="iactivescriptinterruptscriptthread"></a>IActiveScript::InterruptScriptThread
実行中のスクリプトスレッド (イベントシンク、即時実行、またはマクロ呼び出し) の実行を中断します。 このメソッドを使用すると、スタックしているスクリプト (無限ループなど) を終了できます。 基本以外のスレッドから呼び出すことはできません。その結果、非ベースのコールアウトがオブジェクトをホストするか、 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)メソッドになります。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT InterruptScriptThread(  
    SCRIPTTHREADID   stidThread,  // identifier of thread  
    const EXCEPINFO *pexcepinfo,  // receives error information  
    DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stidThread`  
 から中断するスレッドの識別子、または次の特殊なスレッド識別子の値のいずれか。  
  
|[値]|説明|  
|-----------|-------------|  
|SCRIPTTHREADID_ALL|すべてのスレッド。 割り込みは、現在実行中のすべてのスクリプトメソッドに適用されます。 呼び出し元がスクリプトの切断を要求しない限り、次のスクリプト化されたイベントによって、SCRIPTSTATE_DISCONNECTED または SCRIPTSTATE_INITIALIZED フラグを使用して[IActiveScript:: SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md)メソッドを呼び出すことにより、スクリプトコードが再実行されることに注意してください。一連.|  
|SCRIPTTHREADID_BASE|基本スレッド。つまり、スクリプトエンジンがインスタンス化されたスレッド。|  
|SCRIPTTHREADID_CURRENT|現在実行中のスレッド。|  
  
 `pexcepinfo`  
 から中止されたスクリプトに報告する必要があるエラー情報を含む `EXCEPINFO` 構造体のアドレス。  
  
 `dwFlags`  
 から中断に関連付けられているオプションフラグ。 次のいずれかの値を指定します。  
  
|[値]|説明|  
|-----------|-------------|  
|SCRIPTINTERRUPT_DEBUG|サポートされている場合は、現在のスクリプト実行ポイントでスクリプトエンジンのデバッガーを入力します。|  
|SCRIPTINTERRUPT_RAISEEXCEPTION|スクリプトエンジンの言語でサポートされている場合は、スクリプトで例外を処理します。 それ以外の場合は、スクリプトメソッドが中止され、エラーコードが呼び出し元に返されます。つまり、イベントソースまたはマクロ呼び出し元です。|  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_UNEXPECTED`|この呼び出しは想定されていませんでした (たとえば、スクリプトエンジンがまだ読み込まれていないか、初期化されていません)。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)
---
title: 'IActiveScript:: GetScriptThreadState |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptThreadState
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptThreadState
ms.assetid: 7cac94d0-436e-4c29-895b-0c4afa0b3ccc
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 38f6ef4b0acdf6e3b746316bef8abe9a3f0f8225
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72578004"
---
# <a name="iactivescriptgetscriptthreadstate"></a>IActiveScript::GetScriptThreadState
スクリプトスレッドの現在の状態を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetScriptThreadState(  
    SCRIPTTHREADID stidThread,    // identifier of script thread  
    SCRIPTTHREADSTATE *pstsState  // receives state flag  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stidThread`  
 から状態が必要なスレッドの識別子、または次の特殊なスレッド識別子のいずれか。  
  
|[値]|説明|  
|-----------|-------------|  
|SCRIPTTHREADID_BASE|基本スレッド。つまり、スクリプトエンジンがインスタンス化されたスレッド。|  
|SCRIPTTHREADID_CURRENT|現在実行中のスレッド。|  
  
 `pstsState`  
 入出力指定されたスレッドの状態を受け取る変数のアドレス。 状態は、 [SCRIPTTHREADSTATE 列挙](../../winscript/reference/scriptthreadstate-enumeration.md)列挙によって定義された名前付き定数値のいずれかによって示されます。 このパラメーターで現在のスレッドが識別されない場合、状態はいつでも変更される可能性があります。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_UNEXPECTED`|この呼び出しは想定されていませんでした (たとえば、スクリプトエンジンがまだ読み込まれていないか、初期化されていません)。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは非ベースのスレッドから呼び出すことができます。この場合、非ベースのコールアウトによってオブジェクトをホストするか、 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)インターフェイスを使用することはできません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)
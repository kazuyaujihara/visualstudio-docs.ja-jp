---
title: 'IActiveScript:: GetScriptState |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptState
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptState
ms.assetid: 59837f7c-755d-45c4-8194-bd57638fe2e1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d266e713879aafe1c5ca271d46b3030f3275460f
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575734"
---
# <a name="iactivescriptgetscriptstate"></a>IActiveScript::GetScriptState
スクリプトエンジンの現在の状態を取得します。 このメソッドは非ベースのスレッドから呼び出すことができます。この場合、非ベースのコールアウトによってオブジェクトをホストするか、 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)インターフェイスを使用することはできません。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetScriptState(  
    SCRIPTSTATE *pss  // address of structure for state information  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pss`  
 入出力[Scriptstate 列挙](../../winscript/reference/scriptstate-enumeration.md)型で定義されている値を受け取る変数のアドレス。 値は、呼び出し元のスレッドに関連付けられているスクリプトエンジンの現在の状態を示します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は `S_OK` を返します。無効なポインターが指定された場合は `E_POINTER` を返します。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)
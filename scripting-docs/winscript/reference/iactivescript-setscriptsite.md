---
title: Iactivescript::setscriptsite |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.SetScriptSite
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_SetScriptSite
ms.assetid: 47d94c32-09f8-4539-ac56-0236026f627b
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3fdf5f3ae84d1a991d67170b5f2b02114b91ee05
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157069"
---
# <a name="iactivescriptsetscriptsite"></a>IActiveScript::SetScriptSite
スクリプト エンジンに通知、 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)ホストによって提供されるインターフェイスのサイト。 その他の前にこのメソッドを呼び出す[IActiveScript](../../winscript/reference/iactivescript.md)インターフェイス メソッドを使用します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetScriptSite(  
    IActiveScriptSite *pScriptSite  // address of host script site  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pScriptSite`  
 [in]スクリプト エンジンのこのインスタンスに関連するスクリプトのホストが指定したサイトのアドレス。 サイトをこのスクリプト エンジンのインスタンスを一意に割り当てる必要があります。その他のスクリプト エンジンで共有できません。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_FAIL`|不明なエラーが発生しました。スクリプト エンジンは、サイトの初期化を終了できませんでした。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_UNEXPECTED`|呼び出しが予期されていませんでした (たとえば、サイトが既に設定)。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)
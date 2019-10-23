---
title: 'IActiveScript:: SetScriptSite |Microsoft Docs'
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
ms.openlocfilehash: 063dcc7b580334bff9780e9c209b621ef7e25656
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575331"
---
# <a name="iactivescriptsetscriptsite"></a>IActiveScript::SetScriptSite
ホストによって提供される[IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)インターフェイスサイトのスクリプトエンジンに通知します。 他の[IActiveScript](../../winscript/reference/iactivescript.md)インターフェイスメソッドを使用する前に、このメソッドを呼び出してください。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetScriptSite(  
    IActiveScriptSite *pScriptSite  // address of host script site  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pScriptSite`  
 からスクリプトエンジンのこのインスタンスに関連付けられる、ホストが提供するスクリプトサイトのアドレス。 サイトは、このスクリプトエンジンインスタンスに一意に割り当てられている必要があります。他のスクリプトエンジンと共有することはできません。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_FAIL`|特定できないエラーが発生しました。スクリプトエンジンは、サイトの初期化を完了できませんでした。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_UNEXPECTED`|呼び出しは想定されていませんでした (たとえば、サイトが既に設定されています)。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)
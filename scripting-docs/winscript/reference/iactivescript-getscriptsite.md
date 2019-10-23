---
title: 'IActiveScript:: GetScriptSite |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptSite
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptSite
ms.assetid: 83a2a89d-93d0-4cbd-9244-91a730cb406b
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 567c7b5c1ead5388e6ec9c67d6ab6f9f580adf20
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575743"
---
# <a name="iactivescriptgetscriptsite"></a>IActiveScript::GetScriptSite
Windows スクリプトエンジンに関連付けられているサイトオブジェクトを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetScriptSite(  
    REFIID iid,           // interface identifier  
    void **ppvSiteObject  // address of host site interface  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `iid`  
 から要求されたインターフェイスの識別子。  
  
 `ppvSiteObject`  
 入出力ホストのサイトオブジェクトへのインターフェイスポインターを受け取る場所のアドレス。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_NOINTERFACE`|指定されたインターフェイスはサポートされていません。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`S_FALSE`|サイトが設定されていません。`ppvSiteObject` パラメーターが `NULL` に設定されています。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)
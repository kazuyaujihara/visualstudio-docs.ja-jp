---
title: IActiveScriptSite::GetDocVersionString |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.GetDocVersionString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_GetDocVersionString
ms.assetid: ab3f892d-06d3-4cb5-9ea5-20c4a1e518cd
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7327b71329c1f476eab9c27d5e0d5a047664abfa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992749"
---
# <a name="iactivescriptsitegetdocversionstring"></a>IActiveScriptSite::GetDocVersionString
現在のドキュメントのバージョンを一意に識別するホスト定義の文字列を取得します。 (メモ帳で編集されている HTML ページの大文字と小文字) のように Windows スクリプトのスコープ外関連のドキュメントを変更した場合は、スクリプト エンジン保存できますこのと共に強制的に再コンパイル、スクリプトが読み込まれる、次回の永続化された状態。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDocVersionString(  
    BSTR *pbstrVersionString  // address of document version string  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstrVersionString`  
 [out]ホストが定義するドキュメントのバージョン文字列のアドレス。  
  
## <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、または`E_NOTIMPL`場合、このメソッドはサポートされていません。  
  
## <a name="remarks"></a>Remarks  
 場合`E_NOTIMPL`返されるか、スクリプト エンジンでは、スクリプトは、ドキュメントとの同期にすると想定する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
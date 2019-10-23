---
title: 'IActiveScriptSite:: GetDocVersionString |Microsoft Docs'
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
ms.openlocfilehash: 8ecc592b6b7fcae5f516a3c1dd111c027e67b6dc
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571134"
---
# <a name="iactivescriptsitegetdocversionstring"></a>IActiveScriptSite::GetDocVersionString
現在のドキュメントのバージョンを一意に識別するホスト定義の文字列を取得します。 関連ドキュメントが Windows スクリプトのスコープ外で変更された場合 (メモ帳で編集されている HTML ページの場合のように)、スクリプトエンジンは永続化された状態と共にこれを保存し、次回スクリプトが読み込まれるときに再コンパイルを強制することができます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDocVersionString(  
    BSTR *pbstrVersionString  // address of document version string  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstrVersionString`  
 入出力ホスト定義ドキュメントのバージョン文字列のアドレス。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は `S_OK` を返します。このメソッドがサポートされていない場合は `E_NOTIMPL` を返します。  
  
## <a name="remarks"></a>Remarks  
 @No__t_0 が返された場合、スクリプトエンジンは、スクリプトがドキュメントと同期していると想定する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
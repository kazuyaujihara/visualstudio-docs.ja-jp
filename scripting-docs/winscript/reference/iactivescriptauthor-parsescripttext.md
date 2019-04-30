---
title: IActiveScriptAuthor::ParseScriptText |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.ParseScriptText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::ParseScriptText
ms.assetid: ebe212e8-6789-423d-ad22-92be984dc7ad
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe6870f3b19c5727fdbea0418b8373b990cb671a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955083"
---
# <a name="iactivescriptauthorparsescripttext"></a>IActiveScriptAuthor::ParseScriptText
スクリプトのテキストを解析しますが、テキスト エンジンを作成するスクリプトを追加、作成して、`IScriptEntry`スクリプト ブロックに対応するオブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT ParseScriptText(  
   LPCOLESTR pszCode,  
   LPCOLESTR pszItemName,  
   LPCOLESTR pszDelimiter,  
   DWORD dwCookie,  
   DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszCode`  
 [in]スクリプトのテキストを解析します。  
  
 `pszItemName`  
 [in]スクリプト ブロックに関連付けられている項目の名前を含むバッファーのアドレス。  
  
 `pszDelimiter`  
 [in]最後のスクリプト ブロックの区切り記号のアドレス。 ときに`pszCode`解析は、テキストのストリームからホスト通常 (など、2 つ単一引用符)、区切り記号を使用して、スクリプト ブロックの終了を検出します。 スクリプト ブロックの末尾を識別する区切り記号がない場合は、このパラメーターを NULL に設定します。  
  
 `dwCookie`  
 [in]アプリケーション定義の値に関連付けられた新しい`IScriptEntry`オブジェクト。  
  
 `dwFlags`  
 [in]使用されません。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptAuthor インターフェイス](../../winscript/reference/iactivescriptauthor-interface.md)
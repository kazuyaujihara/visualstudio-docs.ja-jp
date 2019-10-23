---
title: IActiveScriptAuthor::P arseScriptText |Microsoft Docs
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
ms.openlocfilehash: 90d5ab0fa700ed29b5fb37b1c48617cedec871b9
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576151"
---
# <a name="iactivescriptauthorparsescripttext"></a>IActiveScriptAuthor::ParseScriptText
スクリプトテキストを解析し、スクリプト作成エンジンにテキストを追加し、スクリプトブロックに対応する `IScriptEntry` オブジェクトを作成します。  
  
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
 から解析するスクリプトテキスト。  
  
 `pszItemName`  
 からスクリプトブロックに関連付けられている項目名を格納しているバッファーアドレス。  
  
 `pszDelimiter`  
 からスクリプトの終了ブロックの区切り記号のアドレス。 テキストのストリームから `pszCode` を解析する場合、ホストは通常、スクリプトブロックの終了を検出するために区切り記号 (2 つの単一引用符など) を使用します。 スクリプトブロックの末尾を識別する区切り記号がない場合は、このパラメーターを NULL に設定します。  
  
 `dwCookie`  
 から新しい `IScriptEntry` オブジェクトに関連付けられているアプリケーション定義の値。  
  
 `dwFlags`  
 から使用しません。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptAuthor インターフェイス](../../winscript/reference/iactivescriptauthor-interface.md)
---
title: 'IActiveScriptAuthor:: AddScriptlet レット |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.AddScriptlet
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::AddScriptlet
ms.assetid: 879a6651-f187-4934-b130-c1247549900b
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a349a848f282e6b3a228c7b17009e0261801be5
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577986"
---
# <a name="iactivescriptauthoraddscriptlet"></a>IActiveScriptAuthor::AddScriptlet
ルートレベル `IScriptNode` オブジェクトの子としてコードスクリプトレットを追加します。 ホストでは、スクリプトレットの完全修飾名には、2つのレベルのみを指定できます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AddScriptlet(  
   LPCOLESTR pszDefaultName,  
   LPCOLESTR pszCode,  
   LPCOLESTR pszItemName,  
   LPCOLESTR pszSubItemName,  
   LPCOLESTR pszEventName,  
   LPCOLESTR pszDelimiter,  
   DWORD dwCookie,  
   DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszDefaultName`  
 からスクリプトレットに関連付ける既定の名前のアドレス。  
  
 `pszCode`  
 からスクリプトレットテキストのアドレス。  
  
 `pszItemName`  
 からホストの完全修飾スクリプトレット名の最上位レベル識別子のバッファーアドレス。  
  
 `pszSubItemName`  
 からホストの完全修飾スクリプトレット名の第2レベル識別子のバッファーアドレス。 名前にレベルが1つしかない場合は NULL に設定します。  
  
 `pszEventName`  
 からスクリプトレットがイベントハンドラーであるイベント名を格納しているバッファーのアドレス。  
  
 `pszDelimiter`  
 からスクリプトの終了ブロックの区切り記号のアドレス。 テキストのストリームから `pszCode` を解析する場合、ホストは通常、スクリプトブロックの終了を検出するために区切り記号 (2 つの単一引用符など) を使用します。 区切り記号がスクリプトブロックの末尾をマークしない場合は、このパラメーターを NULL に設定します。  
  
 `dwCookie`  
 からスクリプトレットをホストオブジェクトに関連付けるために使用されるアプリケーション定義の値。  
  
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
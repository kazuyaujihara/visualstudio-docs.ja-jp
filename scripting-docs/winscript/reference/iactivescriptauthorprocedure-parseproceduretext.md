---
title: IActiveScriptAuthorProcedure::P arseProcedureText |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthorProcedure.ParseProcedureText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthorProcedure::ParseProcedureText
ms.assetid: cb6c29c5-c749-48d7-a6a8-ccbf0f9119ec
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 11a34843f30274ec78f1652c5ed5cd4dbcf2884a
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572818"
---
# <a name="iactivescriptauthorprocedureparseproceduretext"></a>IActiveScriptAuthorProcedure::ParseProcedureText
コードプロシージャを解析し、コードプロシージャのテキストをスクリプト作成エンジンに追加し、コードプロシージャに対応する `IScriptEntry` オブジェクトを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT ParseProcedureText(  
   LPCOLESTR   pszCode,  
   LPCOLESTR   pszFormalParams,  
   LPCOLESTR   pszProcedureName,  
   LPCOLESTR   pszItemName,  
   LPCOLESTR   pszDelimiter,  
   DWORD       dwCookie,  
   DWORD       dwFlags,  
   IDispatch   *pdispFor  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszCode`  
 から解析するスクリプトテキスト。  
  
 `pszFormalParams`  
 からプロシージャの仮パラメーター名のアドレス。 パラメーター名は、スクリプト作成エンジンの適切な区切り記号で区切る必要があります。 名前をかっこで囲むことはできません。  
  
 `pszProcedureName`  
 から解析するプロシージャ名のアドレス。  
  
 `pszItemName`  
 から@No__t_0 オブジェクトに関連付けられている項目名を格納しているバッファーアドレス。  
  
 `pszDelimiter`  
 からスクリプトの終了ブロックの区切り記号のアドレス。 テキストのストリームから `pszCode` を解析する場合、ホストは通常、スクリプトブロックの終了を検出するために区切り記号 (2 つの単一引用符など) を使用します。 スクリプトブロックの末尾を示す区切り記号がない場合は、このパラメーターを NULL に設定します。  
  
 `dwCookie`  
 から新しい `IScriptEntry` オブジェクトに関連付けられているアプリケーション定義の値。  
  
 `dwFlags`  
 から使用しません。  
  
 `pdispFor`  
 から使用しません。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 現在の [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] エンジンは、このメソッドを実装していません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptAuthorProcedure インターフェイス](../../winscript/reference/iactivescriptauthorprocedure-interface.md)
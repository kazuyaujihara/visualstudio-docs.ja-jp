---
title: 'IActiveScriptAuthor:: GetChars |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetChars
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetChars
ms.assetid: a73ba263-12f7-4d5f-b4c8-9ad7e2d5d3cb
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ce2b46d65c2ce92111bc4b6f44f66ce9dc4ce5f
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576251"
---
# <a name="iactivescriptauthorgetchars"></a>IActiveScriptAuthor::GetChars
要求された完了コンテキストの完了文字のセットを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetChars(  
   DWORD            fRequestedList,  
   BSTR             *pbstrChars  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fRequestedList`  
 から要求された完了コンテキスト。  
  
|定数|[値]|説明|  
|--------------|-----------|-----------------|  
|SCRIPT_CMPL_ENUM_TRIGGER|0x0001|左辺の列挙を要求します。|  
|SCRIPT_CMPL_MEMBER_TRIGGER|0x0002|メンバーの完了コンテキストを要求します。|  
|SCRIPT_CMPL_PARAM_TRIGGER|0x0003|パラメーターリストを要求します。|  
|SCRIPT_CMPL_COMMIT|0x0004|パラメーターリストの完了を要求します。|  
  
 `pbstrChars`  
 入出力要求された完了コンテキストに対応する文字。  
  
|`fRequestedList` パラメーター|返される文字|  
|--------------------------------|-------------------------|  
|SCRIPT_CMPL_ENUM_TRIGGER|"."|  
|SCRIPT_CMPL_MEMBER_TRIGGER|"="|  
|SCRIPT_CMPL_PARAM_TRIGGER|"(,"|  
|SCRIPT_CMPL_COMMIT|"()"|  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptAuthor インターフェイス](../../winscript/reference/iactivescriptauthor-interface.md)
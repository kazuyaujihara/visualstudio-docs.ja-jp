---
title: 'IDispatchEx:: GetDispID |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetDispID
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetDispID method
ms.assetid: a288d63d-b08a-4540-9d9d-0bcd182eff9a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 57f0faf6004e2219600f0dbd63749a7e65ca438c
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576596"
---
# <a name="idispatchexgetdispid"></a>IDispatchEx::GetDispID
1つのメンバー名を対応する DISPID にマップします。これは、後続の `IDispatchEx::InvokeEx` への呼び出しで使用できます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDispID(  
   BSTR bstrName,  
   DWORD grfdex,  
   DISPID *pid  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `bstrName`  
 マップされる名前が渡されました。  
  
 `grfdex`  
 メンバー識別子を取得するためのオプションを決定します。 次の値の組み合わせを指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|fdexNameCaseSensitive|大文字と小文字を区別する方法で名前の参照を実行するように要求します。 大文字と小文字を区別する検索をサポートしていないオブジェクトによって無視される場合があります。|  
|fdexNameEnsure|メンバーが存在しない場合に作成されることを要求します。 新しいメンバーは `VT_EMPTY` 値を使用して作成する必要があります。|  
|fdexNameImplicit|ベースオブジェクトが明示的に指定されていない場合に、呼び出し元が特定の名前のメンバーのオブジェクトを検索していることを示します。|  
|fdexNameCaseInsensitive|大文字と小文字を区別せずに名前参照を実行するように要求します。 大文字と小文字を区別しない検索をサポートしていないオブジェクトによって無視される場合があります。|  
  
 `pid`  
 DISPID の結果を受信するために、呼び出し元に割り当てられた場所へのポインター。 エラーが発生した場合、`pid` には DISPID_UNKNOWN が含まれます。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|||  
|-|-|  
|`S_OK`|成功。|  
|`E_OUTOFMEMORY`|メモリが不足しています。|  
|`DISP_E_UNKNOWNNAME`|名前が不明です。|  
  
## <a name="remarks"></a>Remarks  
 指定されたメンバーの DISPID を取得するために、`GetIDsOfNames` の代わりに `GetDispID` を使用できます。  
  
 @No__t_0 によってメンバーの追加と削除が許可されるため、Dispid のセットは、オブジェクトの有効期間にわたって一定のままになりません。  
  
 @No__t_1 の未使用の `riid` パラメーターが削除されました。  
  
## <a name="example"></a>例  
  
```cpp
BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;   
  
   // Assign to pdex and bstrName  
   pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid);  
   // Use dispid  
```  
  
## <a name="see-also"></a>関連項目  
 [IDispatchEx インターフェイス](../../winscript/reference/idispatchex-interface.md)
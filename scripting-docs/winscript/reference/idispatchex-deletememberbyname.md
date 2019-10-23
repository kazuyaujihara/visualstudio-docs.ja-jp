---
title: IDispatchEx::D eleteMemberByName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.DeleteMemberByName
apilocation:
- scrobj.dll
helpviewer_keywords:
- DeleteMemberByName method
ms.assetid: a01b4e6a-d989-4b29-bb3f-04554f8c39f7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2abb562f65885ee1d12f2ec9b2300fcddd3be37b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576618"
---
# <a name="idispatchexdeletememberbyname"></a>IDispatchEx::DeleteMemberByName
メンバーを名前で削除します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT DeleteMemberByName(  
   BSTR bstrName,  
   DWORD grfdex  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `bstrName`  
 削除するメンバーの名前。  
  
 `grfdex`  
 メンバー名で大文字と小文字を区別するかどうかを指定します。 次のいずれかの値を指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|fdexNameCaseSensitive|大文字と小文字を区別する方法で名前の参照を実行するように要求します。 大文字と小文字を区別する検索をサポートしていないオブジェクトによって無視される可能性があります。|  
|fdexNameCaseInsensitive|大文字と小文字を区別せずに名前参照を実行するように要求します。 大文字と小文字を区別しない検索をサポートしていないオブジェクトによって無視される可能性があります。|  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|||  
|-|-|  
|`S_OK`|成功。|  
|`S_FALSE`|メンバーは存在しますが、削除できません。|  
  
## <a name="remarks"></a>Remarks  
 メンバーが削除された場合、DISPID は `GetNextDispID` に対して有効なままである必要があります。  
  
 指定された名前のメンバーが削除され、後で同じ名前のメンバーが再作成される場合、DISPID は同じである必要があります。 (大文字と小文字のみが異なるメンバーが "同じ" であるかどうかは、オブジェクトに依存します)。  
  
## <a name="example"></a>例  
  
```cpp
BSTR bstrName;  
IDispatchEx *pdex;  
  
// Assign to pdex and bstrName  
pdex->DeleteMemberByName(bstrName, fdexNameCaseSensitive);  
```  
  
## <a name="see-also"></a>関連項目  
 [IDispatchEx インターフェイス](../../winscript/reference/idispatchex-interface.md)
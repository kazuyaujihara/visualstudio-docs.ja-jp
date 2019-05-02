---
title: IDebugBinder3::FindAlias |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugBinder3::FindAlias
helpviewer_keywords:
- IDebugBinder3::FindAlias method
ms.assetid: b8333701-2718-4983-8513-0875fb7cb730
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 47aaaec73d2c364e974b7430335404bf8caf406c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58978348"
---
# <a name="idebugbinder3findalias"></a>IDebugBinder3::FindAlias
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このメソッドは、名前、別名を検索します。 これでは、すべてのエイリアスをプログラムで検索します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT FindAlias(  
   LPCOLESTR     pcstrName,  
   IDebugAlias** ppAlias  
);  
```  
  
```csharp  
int FindAlias(  
   string          pcstrName,  
   out IDebugAlias ppAlias  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pcstrName`  
 [in]検索するエイリアスの名前です。  
  
 `ppAlias`  
 [out]エイリアス (あれば) が見つかりましたがによって表される、 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)インターフェイス。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`(エイリアスが存在しない) 場合はエラー コード。  
  
## <a name="remarks"></a>Remarks  
 このメソッドを呼び出す; 前に null 先となるオブジェクトを初期化しますエイリアスが見つかったかどうかを決定した後に null 値をテストします。  
  
## <a name="see-also"></a>関連項目  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)

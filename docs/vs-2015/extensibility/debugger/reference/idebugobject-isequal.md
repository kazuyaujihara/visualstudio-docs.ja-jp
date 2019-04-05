---
title: IDebugObject::IsEqual |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugObject::IsEqual
helpviewer_keywords:
- IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 85252cdaf9fb076ebd4f8000115bcea576531bb1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973772"
---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このオブジェクトを持つオブジェクトを比較します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT IsEqual(   
   IDebugObject* pObject,  
   BOOL*         pfIsEqual  
);  
```  
  
```csharp  
int IsEqual(  
   IDebugObject pObject,  
   out int      pfIsEqual  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pObject`  
 [in][IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)と比較するオブジェクトを表すオブジェクト。  
  
 `pfIsEqual`  
 [out]0 以外を返します (`TRUE`) のオブジェクトの値がそれ以外の場合は 0 を返します (`FALSE`)。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 通常、このメソッドはによって表される値のアドレスを比較できる、`pObject`パラメーターとこの[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)オブジェクトは、アドレスが等しいかどうかは、オブジェクトを等しい。  
  
## <a name="see-also"></a>関連項目  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)

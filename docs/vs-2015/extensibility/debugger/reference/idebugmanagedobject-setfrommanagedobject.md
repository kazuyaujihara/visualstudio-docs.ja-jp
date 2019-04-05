---
title: IDebugManagedObject::SetFromManagedObject |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugManagedObject::SetFromManagedObject
helpviewer_keywords:
- IDebugManagedObject::SetFromManagedObject method
ms.assetid: 8700ee8d-2704-4580-bccc-046837a24edd
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5fa81c34f18d6f1d3980da8d53c65f5ef58c05f3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58978385"
---
# <a name="idebugmanagedobjectsetfrommanagedobject"></a>IDebugManagedObject::SetFromManagedObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

パラメーターとして指定された値クラスのインスタンスから値クラスのオブジェクトのインスタンスの値を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT SetFromManagedObject(   
   IUnknown* pManagedObject  
);  
```  
  
```csharp  
int SetFromManagedObject(  
   object pManagedObject  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pManagedObject`  
 [in]新しい値を格納しているマネージ オブジェクトを表すインターフェイス。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドの使用によって表されるマネージ オブジェクトの変更を[IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)

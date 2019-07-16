---
title: IDebugObject::GetManagedDebugObject |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4f2917135f5e25648cf08cd9030e3fdf31aedb52
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68162472"
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

デバッグ エンジンのアドレス空間には、管理対象のオブジェクトのコピーを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetManagedDebugObject(   
   IDebugManagedObject** ppObject  
);  
```  
  
```csharp  
int GetManagedDebugObject(  
   out IDebugManagedObject ppObject  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppObject`  
 [out]返します、 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)新しく作成されたマネージ オブジェクトを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。 E_FAIL が返された場合は、この[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)マネージ値クラスのインスタンスは表しません。  
  
## <a name="remarks"></a>Remarks  
 これは、 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)オブジェクトなどで、管理対象の値クラスのインスタンスを表す必要があります、`System.Decimal`インスタンス。 呼び出し元のオーバーヘッドがローカル コピーをすることで[Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)がなくなります。  
  
## <a name="see-also"></a>関連項目  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)

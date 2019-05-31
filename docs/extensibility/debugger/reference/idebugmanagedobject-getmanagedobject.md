---
title: IDebugManagedObject::GetManagedObject |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugManagedObject::GetManagedObject
helpviewer_keywords:
- IDebugManagedObject::GetManagedObject method
ms.assetid: 6abe1402-6aad-41e6-8ec1-ae12d5945992
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 75e0367aaddb28e2af2703904fd77b4e4f9f6322
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66349406"
---
# <a name="idebugmanagedobjectgetmanagedobject"></a>IDebugManagedObject::GetManagedObject
管理対象のオブジェクトを表すインターフェイスを返します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetManagedObject( 
   IUnknown** ppManagedObject
);
```

```cpp
int GetManagedObject(
   out object ppManagedObject
);
```

## <a name="parameters"></a>パラメーター
`ppManagedObject`\
[out]管理対象のオブジェクトを表すインターフェイスを返します。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドから返されるインターフェイスは、そのメソッドを呼び出せるように、マネージ クラスによって実装されるインターフェイスの照会できます。

## <a name="see-also"></a>関連項目
- [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)
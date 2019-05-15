---
title: IDebugArrayObject::GetElements |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetElements
helpviewer_keywords:
- IDebugArrayObject::GetElements method
ms.assetid: f6a6262f-5183-46ce-8a45-33ef46088b98
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: bae57db294d52eb476baa32b63e27c6e8b287071
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615325"
---
# <a name="idebugarrayobjectgetelements"></a>IDebugArrayObject::GetElements
配列のすべての要素の列挙子を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetElements( 
   IEnumDebugObjects** ppEnum
);
```

```csharp
int GetElements(
   out IEnumDebugObjects ppEnum
);
```

## <a name="parameters"></a>パラメーター
`ppEnum`\
[out]返します、 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)により、すべての要素を列挙するオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 代わりに、使用、 [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md)と[GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)要素を反復処理するメソッド。

## <a name="see-also"></a>関連項目
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
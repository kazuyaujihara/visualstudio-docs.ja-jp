---
title: IDebugArrayObject::GetCount |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetCount
helpviewer_keywords:
- IDebugArrayObject::GetCount method
ms.assetid: 7931f3f7-033c-4bf8-8abd-95183952ebb0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30419e20b6ac1519e3d9b278aabfcb012372d193
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56715012"
---
# <a name="idebugarrayobjectgetcount"></a>IDebugArrayObject::GetCount
配列内の要素数を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetCount( 
   DWORD* pdwElements
);
```

```csharp
int GetCount(
   out uint pdwElements
);
```

#### <a name="parameters"></a>パラメーター
 `pdwElements`

 [out]数を返します。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、1 次元の配列として配列オブジェクトが多次元である場合でもすべて配列オブジェクトの要素のように表示されます。 たとえば、配列を指定`myarray[3][2][6]`、メソッドはで 36、`pdwElements`パラメーター。 使用して、 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)メソッドに一度に 1 つの個々 の要素を取得します。

## <a name="see-also"></a>関連項目
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
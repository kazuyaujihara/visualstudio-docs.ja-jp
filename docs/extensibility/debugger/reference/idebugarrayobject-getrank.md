---
title: IDebugArrayObject::GetRank |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetRank
helpviewer_keywords:
- IDebugArrayObject::GetRank method
ms.assetid: 9948551a-e334-4ff6-979c-08dab633b9b6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a0391030e77e5959fdc28c94f63e099e5c505d77
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62923729"
---
# <a name="idebugarrayobjectgetrank"></a>IDebugArrayObject::GetRank
つまり、ディメンションの数、配列のランクを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetRank( 
   DWORD* pdwRank
);
```

```csharp
int GetRank(
   out uint pdwRank
);
```

#### <a name="parameters"></a>パラメーター
 `pdwRank`

 [out]順位を返します。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 使用して、 [GetDimensions](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md)配列オブジェクトの各次元のサイズを取得します。

## <a name="see-also"></a>関連項目
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
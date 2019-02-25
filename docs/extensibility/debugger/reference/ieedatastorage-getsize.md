---
title: IEEDataStorage::GetSize |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEDataStorage::GetSize
helpviewer_keywords:
- IEEDataStorage::GetSize
ms.assetid: 33d232c4-1239-4abc-922b-e1bc5b908169
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eff31ef70fc8cb812ff820a92653b6bb0cab6cd5
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719497"
---
# <a name="ieedatastoragegetsize"></a>IEEDataStorage::GetSize
このオブジェクトに含まれるバイト数を返します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetSize(
   ULONG* size
);
```

```csharp
int GetSize(
   out uint size
);
```

#### <a name="parameters"></a>パラメーター
 `size`

 [out]このオブジェクトに含まれるバイト数。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 使用して、 [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)実際のデータのバイト数を取得します。

## <a name="see-also"></a>関連項目
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
- [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)
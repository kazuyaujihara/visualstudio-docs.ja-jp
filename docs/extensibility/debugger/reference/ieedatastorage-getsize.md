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
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 87818a12945e76f68ba3b96a7f90c38640a0aa39
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66199253"
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

## <a name="parameters"></a>パラメーター
`size`\
[out]このオブジェクトに含まれるバイト数。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 使用して、 [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)実際のデータのバイト数を取得します。

## <a name="see-also"></a>関連項目
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
- [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)
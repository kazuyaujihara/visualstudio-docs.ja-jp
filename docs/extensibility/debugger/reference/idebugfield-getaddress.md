---
title: IDebugField::GetAddress |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetAddress
helpviewer_keywords:
- IDebugField::GetAddress method
ms.assetid: 6981bf03-66ef-4bf9-87ea-f6c9624486cb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 417e19eb9c7d014b6c1ca353147f6a8ac96f222e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678268"
---
# <a name="idebugfieldgetaddress"></a>IDebugField::GetAddress
このメソッドは、フィールドのデバッグ アドレスを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetAddress( 
   IDebugAddress** ppAddress
);
```

```csharp
int GetAddress(
   out IDebugAddress ppAddress
);
```

#### <a name="parameters"></a>パラメーター
 `ppAddress`

 [out]アドレスを返します、 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)オブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
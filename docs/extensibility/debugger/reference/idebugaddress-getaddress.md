---
title: IDebugAddress::GetAddress |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress::GetAddress
helpviewer_keywords:
- IDebugAddress:GetAddress method
ms.assetid: 2590387b-5d36-4116-9a75-737957b8898e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1cff380759163a38129b92f07752e72904f6bbaf
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684456"
---
# <a name="idebugaddressgetaddress"></a>IDebugAddress::GetAddress
オブジェクトとそのスコープまたはコンテナー内の場所を記述する構造体を返します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetAddress (
   DEBUG_ADDRESS * pAddress
);
```

```csharp
int GetAddress(
   DEBUG_ADDRESS[] pAddress
);
```

#### <a name="parameters"></a>パラメーター
 `pAddress`

 [入力、出力]A [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)にこのメソッドによって入力される構造体。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)このメソッドは、適切な情報でサインインし、格納する構造体が渡されます。 この情報を解釈する方法は、返される情報とシンボル ハンドラー自体の種類によって異なります。 参照してください[DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)の詳細。

## <a name="see-also"></a>関連項目
- [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)
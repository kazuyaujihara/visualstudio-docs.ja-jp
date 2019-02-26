---
title: IDebugModule3::SetJustMyCodeState |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule3::SetJustMyCodeState
helpviewer_keywords:
- IDebugModule3::SetJustMyCodeState
ms.assetid: 68f8166d-ef64-49ae-ad5e-79604f43bbd4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5ef9c9b01ab37cce527e55696210438fcaaff9d2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56697729"
---
# <a name="idebugmodule3setjustmycodestate"></a>IDebugModule3::SetJustMyCodeState
かどうかユーザー コードとモジュールをマークします。

## <a name="syntax"></a>構文

```cpp
HRESULT SetJustMyCodeState(
   BOOL fIsUserCode
);
```

```csharp
int SetJustMyCodeState(
   int fIsUserCode
);
```

#### <a name="parameters"></a>パラメーター
 `fIsUserCode`

 [in]0 以外の場合 (`TRUE`) 場合は、モジュールには、ユーザー コードを考慮する必要があります、0 (`FALSE`) が不要な場合。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)
---
title: IEnumDebugObjects::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugObjects::Reset
helpviewer_keywords:
- IEnumDebugObjects::Reset method
ms.assetid: 4a245e47-cc39-4177-b83d-083ea0e3190f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ebeef5502787ad5ab745d72e42205d86320a8f20
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706770"
---
# <a name="ienumdebugobjectsreset"></a>IEnumDebugObjects::Reset
このメソッドは、最初の要素を列挙型をリセットします。

## <a name="syntax"></a>構文

```cpp
HRESULT Reset(void);
```

```csharp
int Reset();
```

#### <a name="parameters"></a>パラメーター
 なし

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドが呼び出された後、次回の呼び出し[次](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)列挙体の最初の要素を返します。

## <a name="see-also"></a>関連項目
- [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)
- [次へ](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)
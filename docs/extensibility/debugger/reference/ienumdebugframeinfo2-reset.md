---
title: IEnumDebugFrameInfo2::Reset |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFrameInfo2::Reset
helpviewer_keywords:
- IEnumDebugFrameInfo2::Reset
ms.assetid: e149b559-f072-480b-9552-a452b147f3a8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a6a39bab8577a8cdcff09d19f90a626791c05114
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225738"
---
# <a name="ienumdebugframeinfo2reset"></a>IEnumDebugFrameInfo2::Reset
最初の要素を列挙値をリセットします。

## <a name="syntax"></a>構文

```cpp
HRESULT Reset(
   void
);
```

```csharp
int Reset();
```

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドが呼び出された後、次回の呼び出し、[次](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)メソッドが列挙体の最初の要素を返します。

## <a name="see-also"></a>関連項目
- [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)
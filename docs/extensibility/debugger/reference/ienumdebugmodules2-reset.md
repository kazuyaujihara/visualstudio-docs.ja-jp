---
title: IEnumDebugModules2::Reset |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugModules2::Reset
helpviewer_keywords:
- IEnumDebugModules2::Reset
ms.assetid: f6ff364c-2644-4919-b950-3cb82eb6f601
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b969b03c955368415d2e5911eb46731d133abad3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350321"
---
# <a name="ienumdebugmodules2reset"></a>IEnumDebugModules2::Reset
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
 このメソッドが呼び出された後、次回の呼び出し、[次](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)メソッドが列挙体の最初の要素を返します。

## <a name="see-also"></a>関連項目
- [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)
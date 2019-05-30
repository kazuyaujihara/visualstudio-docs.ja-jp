---
title: IEnumDebugErrorBreakpoints2::Reset |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugErrorBreakpoints2::Reset
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2::Reset
ms.assetid: d5b04bba-a8b9-4141-94fb-250c77f0534c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8122ec81fd69a0c38a4d1ad0df024d611ddcc49a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66336439"
---
# <a name="ienumdebugerrorbreakpoints2reset"></a>IEnumDebugErrorBreakpoints2::Reset
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
 このメソッドが呼び出された後、次回の呼び出し、[次](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-next.md)メソッドが列挙体の最初の要素を返します。

## <a name="see-also"></a>関連項目
- [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)
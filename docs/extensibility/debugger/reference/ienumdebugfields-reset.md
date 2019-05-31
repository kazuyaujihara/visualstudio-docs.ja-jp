---
title: IEnumDebugFields::Reset |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFields::Reset
helpviewer_keywords:
- IEnumDebugFields::Reset method
ms.assetid: 38ff61e4-0120-42e8-971a-16be6050b425
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c50a5e2ed55bf1550ca4a70bc566fb2504b100a3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350415"
---
# <a name="ienumdebugfieldsreset"></a>IEnumDebugFields::Reset
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
 このメソッドが呼び出された後、次回の呼び出し[次](../../../extensibility/debugger/reference/ienumdebugfields-next.md)列挙体の最初の要素を返します。

## <a name="see-also"></a>関連項目
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [次へ](../../../extensibility/debugger/reference/ienumdebugfields-next.md)
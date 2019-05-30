---
title: IDebugAlias::Dispose |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::Dispose
helpviewer_keywords:
- IDebugAlias::Dispose method
ms.assetid: e84909a4-d378-4f48-bf25-2c014c77c8e3
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c84fc6887eb2594f9665924bd3eafa5452a3135c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66330275"
---
# <a name="idebugaliasdispose"></a>IDebugAlias::Dispose
このエイリアスの削除をマークします。

## <a name="syntax"></a>構文

```cpp
HRESULT Dispose();
```

```csharp
int Dispose();
```

## <a name="parameters"></a>パラメーター
 なし。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドが呼び出されると、エイリアスは使用できなくします。

## <a name="see-also"></a>関連項目
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)
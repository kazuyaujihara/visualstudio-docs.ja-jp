---
title: IDebugAlias::Dispose |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::Dispose
helpviewer_keywords:
- IDebugAlias::Dispose method
ms.assetid: e84909a4-d378-4f48-bf25-2c014c77c8e3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d35b5819aa0354581721f02a931aa7bdf679b70d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714960"
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

#### <a name="parameters"></a>パラメーター
 なし。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドが呼び出されると、エイリアスは使用できなくします。

## <a name="see-also"></a>関連項目
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)
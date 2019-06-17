---
title: IDebugBinder3::FindAlias |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder3::FindAlias
helpviewer_keywords:
- IDebugBinder3::FindAlias method
ms.assetid: b8333701-2718-4983-8513-0875fb7cb730
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8387a3302395d6e25c2b00dd360286e533531168
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66344421"
---
# <a name="idebugbinder3findalias"></a>IDebugBinder3::FindAlias
このメソッドは、名前、別名を検索します。 これでは、すべてのエイリアスをプログラムで検索します。

## <a name="syntax"></a>構文

```cpp
HRESULT FindAlias(
   LPCOLESTR     pcstrName,
   IDebugAlias** ppAlias
);
```

```csharp
int FindAlias(
   string          pcstrName,
   out IDebugAlias ppAlias
);
```

## <a name="parameters"></a>パラメーター
`pcstrName`\
[in]検索するエイリアスの名前です。

`ppAlias`\
[out]エイリアス (あれば) が見つかりましたがによって表される、 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)インターフェイス。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`(エイリアスが存在しない) 場合はエラー コード。

## <a name="remarks"></a>Remarks
 このメソッドを呼び出す; 前に null 先となるオブジェクトを初期化しますエイリアスが見つかったかどうかを決定した後に null 値をテストします。

## <a name="see-also"></a>関連項目
- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)
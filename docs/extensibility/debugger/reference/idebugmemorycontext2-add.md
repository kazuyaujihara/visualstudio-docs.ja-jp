---
title: IDebugMemoryContext2::Add |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2::Add
helpviewer_keywords:
- IDebugMemoryContext2::Add method
- Add method
ms.assetid: 3c47e646-ce9e-4dd3-8f1a-6dbd3827d407
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c1cafbf22e51f867948491e2925c085bd387ea84
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347086"
---
# <a name="idebugmemorycontext2add"></a>IDebugMemoryContext2::Add
現在のコンテキストに指定した値を追加し、新しいコンテキストを返します。

## <a name="syntax"></a>構文

```cpp
HRESULT Add( 
   UINT64                 dwCount,
   IDebugMemoryContext2** ppMemCxt
);
```

```csharp
int Add(
   ulong                    dwCount,
   out IDebugMemoryContext2 ppMemCxt
);
```

## <a name="parameters"></a>パラメーター
`dwCount`\
[in]現在のコンテキストに追加する値。

`ppMemCxt`\
[out]新しいを返します[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)オブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 メモリのコンテキストは、コンテキストの新しいインターフェイスを必要とする新しいアドレスを生成するアドレスに値を追加するために、アドレスです。

 結果として得られるアドレスがこのコンテキストに関連付けられたメモリ空間の外にある場合でも、新しいコンテキストをこのメソッドを生成することが常にする必要があります。 唯一の例外は、新しいコンテキストのメモリを割り当てることはできませんか場合`ppMemCxt`は (つまり、エラー)、null 値です。

## <a name="see-also"></a>関連項目
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
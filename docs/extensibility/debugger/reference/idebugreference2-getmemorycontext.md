---
title: IDebugReference2::GetMemoryContext |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::GetMemoryContext
helpviewer_keywords:
- IDebugReference2::GetMemoryContext
ms.assetid: 47fc3827-07a0-4eee-b7f4-fc1c62e6b25c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fd4494b21d4b5b3aa3f73cbabed771f2fac7280c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62869007"
---
# <a name="idebugreference2getmemorycontext"></a>IDebugReference2::GetMemoryContext
メモリ参照のコンテキストを取得します。 将来使用するために予約されています。

## <a name="syntax"></a>構文

```cpp
HRESULT GetMemoryContext ( 
   IDebugMemoryContext2** ppMemory
);
```

```csharp
int GetMemoryContext ( 
   out IDebugMemoryContext2 ppMemory
);
```

#### <a name="parameters"></a>パラメーター
 `ppMemory`

 [out]返します、 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)参照の値に関連付けられているメモリを表すオブジェクト。

## <a name="return-value"></a>戻り値
 常に `E_NOTIMPL` を返します。

## <a name="see-also"></a>関連項目
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
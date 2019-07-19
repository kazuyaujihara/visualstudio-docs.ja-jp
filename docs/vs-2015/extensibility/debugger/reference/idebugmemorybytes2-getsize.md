---
title: IDebugMemoryBytes2::GetSize |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryBytes2::GetSize
helpviewer_keywords:
- IDebugMemoryBytes2::GetSize method
- GetSize method
ms.assetid: dae64c5f-5b54-40c3-b32f-ec3b16c093f7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0e4a1772b4cba1863a0e3d93b269e827f4d00568
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68180554"
---
# <a name="idebugmemorybytes2getsize"></a>IDebugMemoryBytes2::GetSize
これによって表されるメモリのバイト単位のサイズを取得[IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)オブジェクト。

## <a name="syntax"></a>構文

```cpp
HRESULT GetSize( 
   UINT64* pqwSize
);
```

```csharp
int GetSize(
   out ulong pqwSize
);
```

#### <a name="parameters"></a>パラメーター
 `pqwSize`

 [out]バイトのメモリ領域で、サイズを返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)
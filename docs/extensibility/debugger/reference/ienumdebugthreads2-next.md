---
title: IEnumDebugThreads2::Next |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugThreads2::Next
helpviewer_keywords:
- IEnumDebugThreads2::Next
ms.assetid: bcffd954-3c67-4867-96f3-041ddb3e34d4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2cdc06c8517442047778f2cc023478ede70b2a60
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62865929"
---
# <a name="ienumdebugthreads2next"></a>IEnumDebugThreads2::Next
列挙体から次の要素のセットを返します。

## <a name="syntax"></a>構文

```cpp
HRESULT Next(
   ULONG           celt,
   IDebugThread2** rgelt,
   ULONG*          pceltFetched
);
```

```csharp
int Next(
   uint            celt,
   IDebugThread2[] rgelt,
   ref uint        pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 `celt`

 [in]取得する要素の数。 最大サイズを指定します、`rgelt`配列。

 `rgelt`

 [入力、出力]配列[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)情報を格納する要素。

 `pceltFetched`

 [out]実際に返される要素の数を返します`rgelt`します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`返される可能性があります、要求された要素数よりも少ない場合、それ以外の場合、エラー コードを返します。

## <a name="see-also"></a>関連項目
- [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
---
title: IDebugThread2::Resume |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::Resume
helpviewer_keywords:
- IDebugThread2::Resume
ms.assetid: 36aad682-b0b9-40a2-b3fc-f0e61d41cdbc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4997b8c711a67a3bb45529627e81e70b786acf00
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62915510"
---
# <a name="idebugthread2resume"></a>IDebugThread2::Resume
スレッドの実行を再開します。

## <a name="syntax"></a>構文

```cpp
HRESULT Resume ( 
   DWORD *pdwSuspendCount
);
```

```csharp
int Resume ( 
   out uint pdwSuspendCount
);
```

#### <a name="parameters"></a>パラメーター
 `pdwSuspendCount`

 [out]再開操作の後に、中断カウントを返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドをデクリメントする中断カウントを呼び出して各実行が再開に実際には 0 に達すると、どの時点で、までです。 この中断の数が表示されます、**スレッド**デバッグ ウィンドウ。

 このメソッドを呼び出すたびに、必要があります、前回の呼び出し、 [Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md)メソッド。 何回中断カウントの決定、`IDebugThread2::Suspend`メソッドがこれまでに呼び出されます。

## <a name="see-also"></a>関連項目
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md)
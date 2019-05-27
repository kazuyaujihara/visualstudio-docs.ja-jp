---
title: IDebugThread2::Suspend |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::Suspend
helpviewer_keywords:
- IDebugThread2::Suspend
ms.assetid: 1e20be85-aa12-48de-bb83-0bf0976e99ae
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b9df2f37a6e8acb9f8e37d2fbd1a379bc4572b39
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66199464"
---
# <a name="idebugthread2suspend"></a>IDebugThread2::Suspend
スレッドを中断します。

## <a name="syntax"></a>構文

```cpp
HRESULT Suspend ( 
   DWORD *pdwSuspendCount
);
```

```csharp
HRESULT Suspend ( 
   out uint pdwSuspendCount
);
```

## <a name="parameters"></a>パラメーター
`pdwSuspendCount`\
[out]中断操作の後に、中断カウントを返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドを呼び出すたびには、0 より大きい中断カウントがインクリメントします。 この中断の数が表示されます、**スレッド**デバッグ ウィンドウ。

 このメソッドを呼び出すたびに、必要がありますそれ以降の呼び出し、[再開](../../../extensibility/debugger/reference/idebugthread2-resume.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)
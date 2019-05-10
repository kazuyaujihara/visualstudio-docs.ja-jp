---
title: IDebugThread2::GetThreadId |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::GetThreadId
helpviewer_keywords:
- IDebugThread2::GetThreadId
ms.assetid: db8b1c07-6b86-47f9-b292-bac19c276d36
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2ac7e834b948d663ea9b537b36720864f25fe94c
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225962"
---
# <a name="idebugthread2getthreadid"></a>IDebugThread2::GetThreadId
システムのスレッド識別子を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetThreadId (
    DWORD* pdwThreadId
);
```

```csharp
int GetThreadId (
    out uint pdwThreadId
);
```

## <a name="parameters"></a>パラメーター
`pdwThreadId`\

 [out]システムのスレッド識別子を返します。

## <a name="return-value"></a>戻り値
成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
スレッド ID は、プロセスの他のすべてのスレッド間でスレッドを識別するために使用されます。

## <a name="example"></a>例
次の例は、単純なは、このメソッドを実装する方法を示しています。`CProgram`を実装するオブジェクト、 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)インターフェイス。

```cpp
HRESULT CProgram::GetThreadId(DWORD* pdwThreadId) {
    *pdwThreadId = GetCurrentThreadId();
    return NOERROR;
}
```

## <a name="see-also"></a>関連項目
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)

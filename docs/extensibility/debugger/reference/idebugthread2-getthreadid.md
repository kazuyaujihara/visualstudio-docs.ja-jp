---
title: IDebugThread2::GetThreadId |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::GetThreadId
helpviewer_keywords:
- IDebugThread2::GetThreadId
ms.assetid: db8b1c07-6b86-47f9-b292-bac19c276d36
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 66ad2151f6455d758d57c51a387184a9fcce8ec7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66320171"
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

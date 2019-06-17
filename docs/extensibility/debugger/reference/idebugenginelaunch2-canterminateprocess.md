---
title: IDebugEngineLaunch2::CanTerminateProcess |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineLaunch2::CanTerminateProcess
helpviewer_keywords:
- IDebugEngineLaunch2::CanTerminateProcess
ms.assetid: 7973454d-c957-4123-a0ee-80ebcdbbd2d1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2d8f401ae49edb2f77d35104de68280be322a63d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337222"
---
# <a name="idebugenginelaunch2canterminateprocess"></a>IDebugEngineLaunch2::CanTerminateProcess
プロセスが終了するかどうかを決定します。

## <a name="syntax"></a>構文

```cpp
HRESULT CanTerminateProcess ( 
   IDebugProcess2* pProcess
);
```

```csharp
int CanTerminateProcess ( 
   IDebugProcess2 pProcess
);
```

## <a name="parameters"></a>パラメーター
`pProcess`\
[in][IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)終了するプロセスを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外の場合はエラー コードを返します。 返します`S_FALSE`かどうか、エンジンことはできません、プロセスの終了など、アクセスが拒否されたためです。

## <a name="remarks"></a>Remarks
 このメソッドが戻る場合`S_OK`、し、その、 [TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)実際にプロセスを終了するメソッドを呼び出すことができます。

## <a name="see-also"></a>関連項目
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)
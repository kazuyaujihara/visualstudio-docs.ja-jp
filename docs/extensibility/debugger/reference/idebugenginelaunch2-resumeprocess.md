---
title: IDebugEngineLaunch2::ResumeProcess |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineLaunch2::ResumeProcess
helpviewer_keywords:
- IDebugEngineLaunch2::ResumeProcess
ms.assetid: 61ccc14e-75c6-44e7-aae4-57a9aac52089
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 52eabc3732dc1d91dca7d0ed84f2b3e00bb8e17f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351678"
---
# <a name="idebugenginelaunch2resumeprocess"></a>IDebugEngineLaunch2::ResumeProcess
再開では、実行を処理します。

## <a name="syntax"></a>構文

```cpp
HRESULT ResumeProcess ( 
   IDebugProcess2* pProcess
);
```

```csharp
int ResumeProcess ( 
   IDebugProcess2 pProcess
);
```

## <a name="parameters"></a>パラメーター
`pProcess`\
[in][IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)を再開するプロセスを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドを呼び出して、プロセスが起動された後に呼び出されますが、 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)
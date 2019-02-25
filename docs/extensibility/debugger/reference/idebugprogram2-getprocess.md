---
title: IDebugProgram2::GetProcess |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetProcess
helpviewer_keywords:
- IDebugProgram2::GetProcess
ms.assetid: 1d602485-ebaf-451c-9165-f2e226f20a90
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e92dd0c3bf56710b387535f8b5e3984bff930186
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56701512"
---
# <a name="idebugprogram2getprocess"></a>IDebugProgram2::GetProcess
このプログラムがで実行されているプロセスを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetProcess(
   IDebugProcess2** ppProcess
);
```

```csharp
int GetProcess(
   out IDebugProcess2 ppProcess
);
```

#### <a name="parameters"></a>パラメーター
 `ppProcess`

 [out]返します、 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)プロセスを表すインターフェイスです。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 デバッグ エンジン (DE) を実装しない限り、 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)インターフェイスでは、このメソッドの既定の実装を常に返します`E_NOTIMPL`とでが実行されているプロセスのことはできません、DE が判断できないためですこのメソッドの実装を満たします。

 実装する、`IDebugEngineLaunch2`インターフェイスは、DE がプロセスを作成する方法を知る必要がありますを意味のため、DE の実装、 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)インターフェイスがで実行されているどのようなプロセスを把握できます。

## <a name="see-also"></a>関連項目
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)
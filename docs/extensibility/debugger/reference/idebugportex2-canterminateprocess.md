---
title: IDebugPortEx2::CanTerminateProcess |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEx2::CanTerminateProcess
helpviewer_keywords:
- IDebugPortEx2::CanTerminateProcess
ms.assetid: 111f65d8-5a1a-42b3-9de3-dd9bb03a33fd
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: db1a4fedac88208d54d146a6c5b74b847db21866
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311135"
---
# <a name="idebugportex2canterminateprocess"></a>IDebugPortEx2::CanTerminateProcess
プロセスが終了するかどうかを判断します。

## <a name="syntax"></a>構文

```cpp
HRESULT CanTerminateProcess( 
   IDebugProcess2* pPortProcess
);
```

```csharp
HRESULT CanTerminateProcess( 
   IDebugProcess2 pPortProcess
);
```

## <a name="parameters"></a>パラメーター
`pPortProcess`\
[in][IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)終了するプロセスを表すオブジェクト。

## <a name="return-value"></a>戻り値
 返します`S_OK`プロセスを終了する場合を返しますそれ以外の場合、`S_FALSE`します。

## <a name="see-also"></a>関連項目
- [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
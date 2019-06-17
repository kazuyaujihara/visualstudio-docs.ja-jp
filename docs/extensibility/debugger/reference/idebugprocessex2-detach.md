---
title: IDebugProcessEx2::Detach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcessEx2::Detach
helpviewer_keywords:
- IDebugProcessEx2::Detach method
ms.assetid: 66d54c2c-9302-47c8-9975-f30ed988ab29
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2f016c078fcf19ec244fc4c0682d2caee81a2062
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311611"
---
# <a name="idebugprocessex2detach"></a>IDebugProcessEx2::Detach
このメソッドは、セッションがプロセスのデバッグで不要になったをプロセスに通知します。

## <a name="syntax"></a>構文

```cpp
HRESULT Detach( 
   IDebugSession2* pSession
);
```

```csharp
int Detach(
   IDebugSession2 pSession
);
```

## <a name="parameters"></a>パラメーター
`pSession`\
[in]このプロセスからデタッチするセッションを一意に識別する値。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 インターフェイスが渡された`pSession`は cookie としてのみ扱うは、このプロセスにアタッチされた元セッション デバッグ マネージャーを一意に識別する値。 指定されたインターフェイスのメソッドのいずれも機能します。

## <a name="see-also"></a>関連項目
- [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)
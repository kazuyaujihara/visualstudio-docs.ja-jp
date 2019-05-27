---
title: IDebugDefaultPort2::GetPortNotify |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDefaultPort2::GetPortNotify
helpviewer_keywords:
- IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a9c59687e86d236bc22d563c94e2caaedae5decf
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66205127"
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
このメソッドは、取得、 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)このポートのインターフェイス。

## <a name="syntax"></a>構文

```cpp
HRESULT GetPortNotify(
   IDebugPortNotify2** ppPortNotify
);
```

```csharp
int GetPortNotify(
   out IDebugPortNotify2 ppPortNotify
);
```

## <a name="parameters"></a>パラメーター
`ppPortNotify`\
[out][IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)オブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 通常、`QueryInterface`メソッドが実装するオブジェクト、 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)を取得するインターフェイス、 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)インターフェイス。 ただし、別のオブジェクトに必要なインターフェイスが実装される場合があります。 このメソッドは、このような状況を非表示にし、返します、`IDebugPortNotify2`最も適切なオブジェクトからのインターフェイス。

## <a name="see-also"></a>関連項目
- [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)
- [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)
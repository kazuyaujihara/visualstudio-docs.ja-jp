---
title: IDebugProcess3::GetENCAvailableState |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::GetENCAvailableState
helpviewer_keywords:
- IDebugProcess3::GetENCAvailableState
ms.assetid: 98a5d527-8a72-476c-8e92-0bff3d97c195
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fc51b89061dca3c0d3026b391b8d6b0106421542
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66202345"
---
# <a name="idebugprocess3getencavailablestate"></a>IDebugProcess3::GetENCAvailableState
このメソッドは、プロセスの現在のエディット コンティニュの状態を取得します。 カスタム ポート サプライヤーが常に返す必要があります`E_NOTIMPL`します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetENCAvailableState(
   EncUnavailableReason* pReason
);
```

```csharp
int GetENCAvailableState(
   EncUnavailableReason[] pReason
);
```

## <a name="parameters"></a>パラメーター
`pReason`\
[out]値、 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)列挙体。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

> [!NOTE]
> カスタム ポート サプライヤーが常に返す必要があります`E_NOTIMPL`します。

## <a name="remarks"></a>Remarks
 この状態は影響を受ける[DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)します。

## <a name="see-also"></a>関連項目
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)
- [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)
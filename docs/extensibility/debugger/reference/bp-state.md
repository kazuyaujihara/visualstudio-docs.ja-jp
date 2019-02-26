---
title: BP_STATE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_STATE
helpviewer_keywords:
- BP_STATE enumeration
ms.assetid: 08aa6a3f-3e5f-4c83-8eca-7b7b5f8e208d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4117b3cb92eef555d5ed9a6c3e829fb3302924ae
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709253"
---
# <a name="bpstate"></a>BP_STATE
バインドされたブレークポイントの存在を指定し、かどうかには有効に指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
typedef DWORD BP_STATE;
```

```csharp
public enum enum_BP_STATE {
    BPS_NONE     = 0x0000,
    BPS_DELETED  = 0x0001,
    BPS_DISABLED = 0x0002,
    BPS_ENABLED  = 0x0003
};
```

## <a name="members"></a>メンバー
BPS_NONE では、ブレークポイントが存在しないことを指定します。

BPS_DELETED では、ブレークポイントが削除されたことを指定します。

BPS_DISABLED では、ブレークポイントが無効になっていることを指定します。

BPS_ENABLED では、ブレークポイントが有効になっていることを指定します。

## <a name="remarks"></a>Remarks
返される、 [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)

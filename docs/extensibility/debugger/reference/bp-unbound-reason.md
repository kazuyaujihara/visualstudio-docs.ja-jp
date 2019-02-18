---
title: BP_UNBOUND_REASON |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_UNBOUND_REASON
helpviewer_keywords:
- BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ab701ef9886dddc0c2e32aa79092f22ad91d4630
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316068"
---
# <a name="bpunboundreason"></a>BP_UNBOUND_REASON
ブレークポイントがバインドされた理由を説明します。

## <a name="syntax"></a>構文

```cpp
enum enum_BP_UNBOUND_REASON {
    BPUR_UNKNOWN           = 0x0000,
    BPUR_CODE_UNLOADED     = 0x0002,
    BPUR_BREAKPOINT_REBIND = 0x0003,
    BPUR_BREAKPOINT_ERROR  = 0x0004
};
typedef DWORD BP_UNBOUND_REASON;
```

```csharp
public enum enum_BP_UNBOUND_REASON {
    BPUR_UNKNOWN           = 0x0000,
    BPUR_CODE_UNLOADED     = 0x0002,
    BPUR_BREAKPOINT_REBIND = 0x0003,
    BPUR_BREAKPOINT_ERROR  = 0x0004
};
```

## <a name="members"></a>メンバー
BPUR_UNKNOWN  
不明な理由です。

BPUR_CODE_UNLOADED  
ブレークポイントを含むコードがアンロードされました。

BPUR_BREAKPOINT_REBIND  
ブレークポイントが別の場所にバインドされています。 編集後に発生したり、ブレークポイントに移動したとき、またはファイル パスが無効になっているブレークポイントがバインドされている場合は、操作を続行します。

BPUR_ BREAKPOINT_ERROR  
ブレークポイントを判定して、バインド後にエラーが発生されます。 これは管理対象のブレークポイント条件を持つは無効になります。

## <a name="remarks"></a>Remarks
によって返される、 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
[列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)

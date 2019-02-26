---
title: GUID_ARRAY |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GUID_ARRAY structure
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eed39ee4446e66e1e7b1700d97ad680eb62c2523
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56704970"
---
# <a name="guidarray"></a>GUID_ARRAY
使用可能なデバッグ エンジンの一意の識別子の配列について説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct tagGUID_ARRAY
{
    DWORD dwCount;
    GUID *Members;
} GUID_ARRAY;
```

```csharp
public struct GUID_ARRAY
{
    public uint dwCount;
    public Guid Members;
}
```

## <a name="terms"></a>用語
dwCount 配列内の一意の識別子の数。

一意の識別子を含むメンバーの配列。

## <a name="remarks"></a>Remarks
この構造体がによって返される、 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー:Msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)

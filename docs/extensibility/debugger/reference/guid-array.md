---
title: GUID_ARRAY |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GUID_ARRAY structure
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d53413ee56700fe39470d3bbc3229f4b8b668373
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66317527"
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

## <a name="members"></a>メンバー
`dwCount`\
配列内の一意の識別子の数。

`Members`\
一意の識別子を含む配列。

## <a name="remarks"></a>Remarks
この構造体がによって返される、 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー:Msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)

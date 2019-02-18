---
title: ASSEMBLYLOCRESOLUTION |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- ASSEMBLYLOCRESOLUTION
helpviewer_keywords:
- ASSEMBLYLOCRESOLUTION enumeration
ms.assetid: 0bcfe85c-5f37-4a9d-bf2b-141acd96ad67
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: befa1c67aa8d095288d13cb6f309f31b5c2916e5
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316432"
---
# <a name="assemblylocresolution"></a>ASSEMBLYLOCRESOLUTION
アセンブリがある場所を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_ASSEMBLYLOCRESOLUTION {
    ALR_NAME      = 0x0,
    ALR_USERDIR   = 0x1,
    ALR_SHAREDDIR = 0x2,
    ALR_REMOTEDIR = 0x4,
};
typedef DWORD ASSEMBLYLOCRESOLUTION;
```

```csharp
public enum enum_ASSEMBLYLOCRESOLUTION {
    ALR_NAME      = 0x0,
    ALR_USERDIR   = 0x1,
    ALR_SHAREDDIR = 0x2,
    ALR_REMOTEDIR = 0x4,
};
```

## <a name="members"></a>メンバー
ALR_NAME  
アセンブリは、現在の名前空間にあります。

ALR_USERDIR  
アセンブリは、ユーザー ディレクトリ内にあります。

ALR_SHAREDDIR  
アセンブリは共有ディレクトリにあります。

ALR_REMOTEDIR  
アセンブリは、リモート ディレクトリ内にあります。

## <a name="remarks"></a>Remarks
これらの値がによって返される、 [ResolveAssemblyRef](../../../extensibility/debugger/reference/ipropertyproxyeeside-resolveassemblyref.md)と[GetManagedViewerCreationData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata.md)メソッド。

これらの値と組み合わせることができます、`OR`操作。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
[列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[ResolveAssemblyRef](../../../extensibility/debugger/reference/ipropertyproxyeeside-resolveassemblyref.md)  
[GetManagedViewerCreationData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata.md)

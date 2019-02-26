---
title: PDB_TYPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PDB_TYPE
helpviewer_keywords:
- PDB_TYPE structure
ms.assetid: 1c1bb772-77d6-4870-90b2-fd9247d0004e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5972a6da9422917ef61fb07c9124edca24032ee2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56701252"
---
# <a name="pdbtype"></a>PDB_TYPE

この構造体には、PDB シンボルから取得したフィールドの種類に関する情報を指定します。

## <a name="syntax"></a>構文

```cpp
typedef struct _tagTYPE_PDB {
    ULONG32 ulAppDomainID;
    GUID    guidModule;
    DWORD   symid;
} PDB_TYPE;
```

```csharp
public struct PDB_TYPE {
    public uint ulAppDomainID;
    public Guid guidModule;
    public uint symid;
};
```

## <a name="parameters"></a>パラメーター

`ulAppDomainID`

シンボルが元のアプリケーションの ID。 これは、アプリケーションのインスタンスを一意に識別するに使用されます。

`guidModule`

このフィールドが含まれるモジュールの GUID です。

`symid`

このフィールドに対応するシンボルの ID。

## <a name="remarks"></a>Remarks

共用体の一部としてこの構造体が表示されます、 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)ときに構造体、`dwKind`のフィールド、`TYPE_INFO`構造に設定されている`TYPE_KIND_PDB`(からの値、 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)列挙型)。

## <a name="requirements"></a>必要条件

ヘッダー: sh.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目

- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)
- [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)

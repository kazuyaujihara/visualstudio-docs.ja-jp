---
title: BUILT_TYPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BUILT_TYPE
helpviewer_keywords:
- BUILT_TYPE structure
ms.assetid: cc02c32c-0f65-4210-ad25-a9b1899066e8
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ae5c7e1916c77e3743de63df8903e62feea4fe28
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66327322"
---
# <a name="builttype"></a>BUILT_TYPE
この構造体には、メタデータから取得したフィールドの種類に関する情報を指定します。

## <a name="syntax"></a>構文

```cpp
typedef struct _tagTYPE_BUILT {
    ULONG32      ulAppDomainID;
    GUID         guidModule;
    IDebugField* pUnderlyingField;
} BUILT_TYPE;
```

```csharp
public struct BUILT_TYPE {
    public uint        ulAppDomainID;
    public Guid        guidModule;
    public IDebugField pUnderlyingField;
};
```

## <a name="members"></a>メンバー
`ulAppDomainID`\
シンボルが元のアプリケーションの ID。 これは、アプリケーションのインスタンスを一意に識別するに使用されます。

`guidModule`\
このフィールドが含まれるモジュールの GUID です。

`pUnderlyingField`\
[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)この組み込みのフィールドに関連付けられている基になるフィールドを識別するオブジェクト。

## <a name="remarks"></a>Remarks
共用体の一部としてこの構造体が表示されます、 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)ときに構造体、`dwKind`のフィールド、`TYPE_INFO`構造に設定されている`TYPE_KIND_BUILT`(からの値、 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)列挙型)。

## <a name="requirements"></a>必要条件
ヘッダー: sh.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)
- [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)

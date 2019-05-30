---
title: MODULE_FLAGS |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MODULE_FLAGS
helpviewer_keywords:
- MODULE_FLAGS enumeration
ms.assetid: 0e555b42-b846-4dbb-812e-8e3d11c85b2d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4b8080710b3225f025c329e0c5cb42331e1a059f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346802"
---
# <a name="moduleflags"></a>MODULE_FLAGS
モジュールの記述に使用します。

## <a name="syntax"></a>構文

```cpp
enum enum_MODULE_FLAGS { 
   MODULE_FLAG_NONE        = 0x0000,
   MODULE_FLAG_SYSTEM      = 0x0001,
   MODULE_FLAG_SYMBOLS     = 0x0002,
   MODULE_FLAG_64BIT       = 0x0004,
   MODULE_FLAG_OPTIMIZED   = 0x0008,
   MODULE_FLAG_UNOPTIMIZED = 0x0010
};
typedef DWORD MODULE_FLAGS;
```

```csharp
public enum enum_MODULE_FLAGS { 
   MODULE_FLAG_NONE        = 0x0000,
   MODULE_FLAG_SYSTEM      = 0x0001,
   MODULE_FLAG_SYMBOLS     = 0x0002,
   MODULE_FLAG_64BIT       = 0x0004,
   MODULE_FLAG_OPTIMIZED   = 0x0008,
   MODULE_FLAG_UNOPTIMIZED = 0x0010
};
```

## <a name="fields"></a>フィールド
 `MODULE_FLAG_NONE`\
 モジュールは指定されません。

 `MODULE_FLAG_SYSTEM`\
 システム モジュールを指定します。

 `MODULE_FLAG_SYMBOLS`\
 シンボルのモジュールを指定します。

 `MODULE_FLAG_64BIT`\
 64 ビット モジュールを指定します。

 `MODULE_FLAG_OPTIMIZED`\
 モジュールが最適化されているを指定します。 この状態が反映、**モジュール**ウィンドウ。

 `MODULE_FLAG_UNOPTIMIZED`\
 モジュールが最適化されていないことを指定します。 この状態が反映、**モジュール**ウィンドウ。 これは、既定の状態です。

## <a name="remarks"></a>Remarks
 使用、`m_dwModuleFlags`のメンバー、 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)構造体。

 これらのフラグは、演算と組み合わせることがあります`OR`します。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)
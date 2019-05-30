---
title: BPERESI_FIELDS |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BPERESI_FIELDS
helpviewer_keywords:
- BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f9db96713ba8bb0f3cd421c48ef602e25c2d25a1
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350530"
---
# <a name="bperesifields"></a>BPERESI_FIELDS
ブレークポイントの失敗した解像度について取得する情報を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_BPERESI_FIELDS {
    PERESI_BPRESLOCATION = 0x0001,
    BPERESI_PROGRAM      = 0x0002,
    BPERESI_THREAD       = 0x0004,
    BPERESI_MESSAGE      = 0x0008,
    BPERESI_TYPE         = 0x0010,
    BPERESI_ALLFIELDS    = 0xffffffff
};
typedef DWORD BPERESI_FIELDS;
```

```csharp
public enum enum_BPERESI_FIELDS {
    PERESI_BPRESLOCATION = 0x0001,
    BPERESI_PROGRAM      = 0x0002,
    BPERESI_THREAD       = 0x0004,
    BPERESI_MESSAGE      = 0x0008,
    BPERESI_TYPE         = 0x0010,
    BPERESI_ALLFIELDS    = 0xffffffff
};
```

## <a name="fields"></a>フィールド
`PERESI_BPRESLOCATION`\
初期化/使用、 `bpResLocation` (ブレークポイント解像度の位置) フィールドの[BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)構造体。

`BPERESI_PROGRAM`\
初期化/使用、`pProgram`のフィールド、`BP_ERROR_RESOLUTION_INFO`構造体。

`BPERESI_THREAD`\
初期化/使用、`pThread`のフィールド、`BP_ERROR_RESOLUTION_INFO`構造体。

`BPERESI_MESSAGE`\
初期化/使用、`bstrMessage`のフィールド、`BP_ERROR_RESOLUTION_INFO`構造体。

`BPERESI_TYPE`\
初期化/使用、 `dwType` (ブレークポイントの種類) フィールドの`BP_ERROR_RESOLUTION_INFO`構造体。

`BPERESI_ALLFIELDS`\
すべてのフィールドの初期化/使用して、`BP_ERROR_RESOLUTION_INFO`構造体。

## <a name="remarks"></a>Remarks
パラメーターとして渡される、 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)のどのフィールドを示すメソッド、 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)構造体が初期化されるは。

これらの値は、どのフィールドを示すためにも使用、`BP_ERROR_RESOLUTION_INFO`構造体が返されるときに構造体が使用し、無効です。

これらの値は、演算と組み合わせることがあります`OR`します。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)

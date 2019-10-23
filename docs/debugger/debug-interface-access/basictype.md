---
title: BasicType |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BasicType enumeration
ms.assetid: 19ae53ba-cd6e-47b6-9f94-27ae663ce955
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3fff76abdecdd8613a462225278053ef4f6d9694
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745476"
---
# <a name="basictype"></a>BasicType
シンボルの基本型を指定します。

## <a name="syntax"></a>構文

```C++
enum BasicType {
    btNoType   = 0,
    btVoid     = 1,
    btChar     = 2,
    btWChar    = 3,
    btInt      = 6,
    btUInt     = 7,
    btFloat    = 8,
    btBCD      = 9,
    btBool     = 10,
    btLong     = 13,
    btULong    = 14,
    btCurrency = 25,
    btDate     = 26,
    btVariant  = 27,
    btComplex  = 28,
    btBit      = 29,
    btBSTR     = 30,
    btHresult  = 31,
    btChar16   = 32,  // char16_t
    btChar32   = 33,  // char32_t
};
```

## <a name="elements"></a>Elements
btNoType には基本型が指定されていません。

btVoid 基本型は `void` です。

btChar 基本型は `char` (C/C++型) です。

btWChar 基本型はワイド (Unicode) 文字 (`WCHAR`) です。

btInt 基本型は `signed int` (C/C++ type) です。

btUInt 基本型は `unsigned int` (C/C++ type) です。

btFloat 基本型は、浮動小数点数 (`FLOAT`) です。

btBCD 基本型は、バイナリでコード化された10進数 (`BCD`) です。

btBool 基本型はブール値 (`BOOL`) です。

btLong 基本型は `long int` (C/C++型) です。

btULong 基本型は `unsigned long int` (C/C++型) です。

btCurrency 基本型は currency です。

btDate 基本型は日付/時刻 (`DATE`) です。

btVariant 基本型は、変数型の構造体 (`VARIANT`) です。

btComplex 基本型は複素数です。

btBit 基本型はビットです。

btBSTR 基本型は、基本またはバイナリ文字列 (`BSTR`) です。

btHresult 基本型は `HRESULT` です。

## <a name="remarks"></a>Remarks
この列挙体の値は、 [IDiaSymbol:: get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)メソッドによって返されます。

## <a name="requirements"></a>［要件］
ヘッダー: cvconst. h

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)
- [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)

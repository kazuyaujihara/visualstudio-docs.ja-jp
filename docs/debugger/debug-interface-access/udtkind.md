---
title: UdtKind |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 511beae100529f0db555eca0a8ddb995d7a335d1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56636581"
---
# <a name="udtkind"></a>UdtKind
さまざまなユーザー定義型 (UDT) をについて説明します。

## <a name="syntax"></a>構文

```C++
enum UdtKind {
    UdtStruct,
    UdtClass,
    UdtUnion,
    UdtInterface
};
```

## <a name="elements"></a>Elements
UdtStruct UDT は、構造です。

UdtClass UDT は、クラスです。

UdtUnion UDT は、共用体です。

UdtInterface UDT は、インターフェイスです。

## <a name="remarks"></a>解説
この列挙体の値がによって返される、 [idiasymbol::get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)メソッド。

## <a name="requirements"></a>要件
ヘッダー: cvconst.h

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)

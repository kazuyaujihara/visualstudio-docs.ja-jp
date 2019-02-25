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
ms.openlocfilehash: bb649915179bc6e6b767970150df99caff306b4c
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56317732"
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
UdtStruct  
UDT は、構造です。

UdtClass  
UDT は、クラスです。

UdtUnion  
UDT は、共用体です。

UdtInterface  
UDT は、インターフェイスです。

## <a name="remarks"></a>解説
この列挙体の値がによって返される、 [idiasymbol::get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)メソッド。

## <a name="requirements"></a>要件
ヘッダー: cvconst.h

## <a name="see-also"></a>関連項目
[列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)

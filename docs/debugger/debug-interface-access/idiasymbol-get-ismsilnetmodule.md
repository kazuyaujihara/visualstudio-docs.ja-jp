---
title: Idiasymbol::get_ismsilnetmodule |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isMSILNetmodule method
ms.assetid: 593827f3-8437-4a12-ada4-ff715ec95fb2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0cb96291f7a867bcdd0248cc68c2fbccb6ac9f87
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64828794"
---
# <a name="idiasymbolgetismsilnetmodule"></a>IDiaSymbol::get_isMSILNetmodule
モジュールは、.netmodule (メタデータおよびネイティブ シンボルのみを含む Microsoft Intermediate Language (MSIL) モジュール) かどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_isMSILNetmodule(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>パラメーター
 `pFlag`

[out]返します`TRUE`; MSIL モジュールの場合を返しますそれ以外の場合、`FALSE`します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティがシンボルを使用できないことを意味します。

## <a name="remarks"></a>Remarks
 このプロパティは、`SymTagCompilandDetails`記号の型 (を参照してください[CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md))。

## <a name="requirements"></a>必要条件

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|Dia2.h|
|バージョン:|DIA SDK バージョン 8.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)
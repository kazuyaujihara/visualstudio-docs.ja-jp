---
title: Idiasymbol::get_offset |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_offset method
ms.assetid: 8292bb08-4dc8-4663-beb4-258f5d5a448d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0016ca267b3eaf2535896aab1ee58a470a192c9a
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64786710"
---
# <a name="idiasymbolgetoffset"></a>IDiaSymbol::get_offset
シンボルの場所のオフセットを取得します。 使用する場合、 [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)は`LocIsRegRel`または`LocIsBitField`します。

## <a name="syntax"></a>構文

```C++
HRESULT get_offset ( 
   LONG* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]シンボルの場所のバイト オフセットを返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="remarks"></a>Remarks
 以前に判断によって認識されている時点からのオフセットです。 オフセットなど、`LocIsBitField`場所の型は、通常、含んでいるクラスの先頭から。

## <a name="requirements"></a>必要条件

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|Dia2.h|
|バージョン:|DIA SDK v7.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)

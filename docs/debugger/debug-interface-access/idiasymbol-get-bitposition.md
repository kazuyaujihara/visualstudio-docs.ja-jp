---
title: Idiasymbol::get_bitposition |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_bitPosition method
ms.assetid: b0059407-8655-497b-81ca-025595989371
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 521a21b2d3534433fe72ea6bd9578c0e668755ac
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611832"
---
# <a name="idiasymbolgetbitposition"></a>IDiaSymbol::get_bitPosition
位置のビット位置を取得します。 使用するときに、 [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)は`LocIsBitField`します。

## <a name="syntax"></a>構文

```C++
HRESULT get_bitPosition ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]位置のビット位置を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="requirements"></a>要件

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2.h|
|バージョン:|DIA SDK v7.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)
---
title: 'IDiaSymbol:: get_bitPosition |Microsoft Docs'
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
ms.openlocfilehash: 709bb7e57ee6260ffcd7d8b1421526d3dd41052a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740905"
---
# <a name="idiasymbolget_bitposition"></a>IDiaSymbol::get_bitPosition
位置のビット位置を取得します。 [LocationType 列挙](../../debugger/debug-interface-access/locationtype.md)が `LocIsBitField` 場合に使用します。

## <a name="syntax"></a>構文

```C++
HRESULT get_bitPosition ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力位置のビット位置を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

> [!NOTE]
> @No__t_0 の戻り値は、そのシンボルに対してプロパティを使用できないことを意味します。

## <a name="requirements"></a>［要件］

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2|
|バージョン:|DIA SDK v1.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)
---
title: 'IDiaSymbol:: get_baseSymbol |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cabb5a18-bda7-47e8-9e46-5f4718579fc9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 307358522609659a8a95b94a0adf037026f5b948
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740938"
---
# <a name="idiasymbolget_basesymbol"></a>IDiaSymbol::get_baseSymbol
ポインターの基になる記号を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_baseSymbol(
   IDiaSymbol** pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力ポインターの基になるシンボルへのポインター。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaSymbol::get_baseSymbolId](../../debugger/debug-interface-access/idiasymbol-get-basesymbolid.md)
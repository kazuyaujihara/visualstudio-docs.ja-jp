---
title: Idiasymbol::get_reference |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_reference method
ms.assetid: 6a97cb74-6a14-41fd-8e24-2a42d7a1e529
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5a14e3a380c1409be14142ae9ff3711ab03f410f
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64808883"
---
# <a name="idiasymbolgetreference"></a>IDiaSymbol::get_reference
ポインター型が参照するかどうかを指定するフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_reference ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します`TRUE`ポインター型が; の参照を返しますそれ以外の場合、`FALSE`します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
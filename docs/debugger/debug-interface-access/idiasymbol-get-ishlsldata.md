---
title: IDiaSymbol::get_isHLSLData |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4662058b-c505-4ccf-ae03-739a62c814ca
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 03b0bf45d4b8100f4ebfd1d6a61dc73547312fe6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62836704"
---
# <a name="idiasymbolgetishlsldata"></a>IDiaSymbol::get_isHLSLData
このシンボルが上位レベル シェーダー言語 (HLSL) のデータを表すかどうかを指定します。

## <a name="syntax"></a>構文

```C++
HRESULT get_isHLSLData(
   BOOL* pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]ポインターを`BOOL`このシンボルが HLSL のデータを表すかどうかを指定します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
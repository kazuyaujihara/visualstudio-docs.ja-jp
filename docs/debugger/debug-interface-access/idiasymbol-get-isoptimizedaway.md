---
title: IDiaSymbol::get_isOptimizedAway |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c18b1e38-b152-4a13-aba0-59faded5b2e6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b0f8910d35106574912e4a01f7995bfe0f503e3f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56624816"
---
# <a name="idiasymbolgetisoptimizedaway"></a>IDiaSymbol::get_isOptimizedAway
変数が最適化に機能しているかどうかを指定します。

## <a name="syntax"></a>構文

```C++
HRESULT get_isOptimizedAway(
   BOOL* pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]ポインター、`BOOL`変数が最適化に機能しているかどうかを指定します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)

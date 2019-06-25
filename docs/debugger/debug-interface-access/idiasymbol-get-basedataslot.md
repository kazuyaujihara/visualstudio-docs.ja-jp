---
title: IDiaSymbol::get_baseDataSlot |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f9ed21b7-9397-4813-926e-ade11914b06b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 35612c8b4ab4e4ee64673d6058143788f56339fb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62837700"
---
# <a name="idiasymbolgetbasedataslot"></a>IDiaSymbol::get_baseDataSlot
基本データ スロットを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_baseDataSlot(
   DWORD* pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]ポインター、`DWORD`基本データ スロットを保持しています。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
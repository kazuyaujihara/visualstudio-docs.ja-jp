---
title: IDiaSymbol::get_numberOfRows |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf3eb110-d07f-4995-b68b-08290aa67d6f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c9d87445592db3cc566744151ea207bbb64c4906
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62836072"
---
# <a name="idiasymbolgetnumberofrows"></a>IDiaSymbol::get_numberOfRows
マトリックス内の行の数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_numberOfRows(
   DWORD* pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]ポインターを`DWORD`マトリックスの行の数を保持しています。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
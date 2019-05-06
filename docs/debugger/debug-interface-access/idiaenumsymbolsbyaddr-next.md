---
title: Idiaenumsymbolsbyaddr::next |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbolsByAddr::Next method
ms.assetid: a1320587-7ce7-401f-9548-2f8bcece5cc3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e52567eddcbb6c4f372256e66b7b723bc7aa7394
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62833442"
---
# <a name="idiaenumsymbolsbyaddrnext"></a>IDiaEnumSymbolsByAddr::Next
アドレスの順序で次のシンボルを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Next ( 
   ULONG        celt,
   IDiaSymbol** rgelt,
   ULONG*       pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 celt

[in]シンボルを取得する列挙子の数。

 rgelt

[out]格納する配列、 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)必要なシンボルを表すオブジェクト。

 pceltFetched

[out]フェッチされた列挙子の記号の数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`シンボルがある場合。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、フェッチされる要素の数によって、列挙子の位置を更新します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
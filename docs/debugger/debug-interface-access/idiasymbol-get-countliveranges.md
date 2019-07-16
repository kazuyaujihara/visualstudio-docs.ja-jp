---
title: IDiaSymbol::get_countLiveRanges |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_countLiveRanges
ms.assetid: 55f79e1a-d4c2-42cd-ab37-d8253b20e34c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b8cd86edee72f3d25763fd3d19dd9c789e152ed6
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "62837464"
---
# <a name="idiasymbolgetcountliveranges"></a>IDiaSymbol::get_countLiveRanges
ローカル シンボルに関連付けられている有効なアドレス範囲の数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_countLiveRanges ( 
   DWORD* count
);
```

#### <a name="parameters"></a>パラメーター
 `count`

[out]アドレス範囲の数を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="requirements"></a>必要条件
 ヘッダー:Dia2.h

 ライブラリ: diaguids.lib

 DLL: msdia100.dll

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
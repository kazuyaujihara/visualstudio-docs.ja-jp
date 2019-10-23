---
title: 'IDiaEnumLineNumbers:: Next |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Next method
ms.assetid: 363d5b40-1316-4ab8-836f-63637f619e0a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 07402ef7028ecfb7bb5b2c6e33ae06bc98ffe709
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744390"
---
# <a name="idiaenumlinenumbersnext"></a>IDiaEnumLineNumbers::Next
列挙シーケンス内の指定された数の行番号を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Next ( 
   ULONG            celt,
   IDiaLineNumber** rgelt,
   ULONG*           pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 celt

から取得する列挙子内の行番号の数。

 rgelt

入出力目的の行番号を表す[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)オブジェクトの配列を返します。

 pceltFetched

入出力フェッチされた列挙子の行数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 行番号がない場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
- [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)
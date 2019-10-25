---
title: 'IDiaEnumSymbols:: Next |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbols::Next method
ms.assetid: bfe5fe27-6a84-4392-910f-e325146d7552
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c2d754c144ad876890b89ea217bf0ac55ad60b24
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743933"
---
# <a name="idiaenumsymbolsnext"></a>IDiaEnumSymbols::Next
列挙シーケンス内の指定された数のシンボルを取得します。

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

から取得する列挙子内のシンボルの数。

 rgelt

入出力目的のシンボルを表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクトを使用して入力する配列。

 pceltFetched

入出力フェッチされた列挙子内のシンボルの数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 シンボルがなくなった場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="example"></a>例

```C++
IDiaEnumSymbols* pEnum
CComPtr< IDiaSymbol> pSym;
DWORD celt;
pEnum->Next( 1, &pSym, &celt );
```

## <a name="see-also"></a>関連項目
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
---
title: Idiaenumsourcefiles::next |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Next method
ms.assetid: 83bf6317-ff39-4c5c-8987-cba34e7a6983
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 29424c2b12884cae7f803a46e15f7183d9690d96
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56631784"
---
# <a name="idiaenumsourcefilesnext"></a>IDiaEnumSourceFiles::Next
列挙体シーケンス内のソース ファイルの指定した数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Next ( 
   ULONG            celt,
   IDiaSourceFile** rgelt,
   ULONG*           pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 celt

[in]ソース ファイルを取得する列挙子の数。

 rgelt

[out]格納する配列、 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)目的のソース ファイルを表すオブジェクト。

 pceltFetched

[out]フェッチされた列挙子では、ソース ファイルの数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`これ以上のソース ファイルがある場合。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>参照
- [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)
- [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
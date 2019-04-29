---
title: Idiaenumtables::next |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Next method
ms.assetid: 8d7bd359-d33e-4317-9674-d89283efd7de
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 15a9ebbd3a3993568e4b6496e04661a63290399e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62832739"
---
# <a name="idiaenumtablesnext"></a>IDiaEnumTables::Next
列挙体シーケンス内のテーブルの指定した数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Next ( 
   ULONG       celt,
   IDiaTable** rgelt,
   ULONG*      pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 `celt`

[in]取得する列挙子内のテーブルの数。

 `rgelt`

[out]格納する配列、 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)目的のテーブルを表すオブジェクト。

 `pceltFetched`

[out]フェッチされた列挙子では、テーブルの数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`ない複数のテーブルがある場合。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)
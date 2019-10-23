---
title: 'IDiaEnumSegments:: Next |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Next method
ms.assetid: 53f61874-d821-47ab-a1f5-27e982804a6a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 34062b654cbaccec053c5ac50bfb041d37a0f4e6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744199"
---
# <a name="idiaenumsegmentsnext"></a>IDiaEnumSegments::Next
列挙シーケンス内の指定された数のセグメントを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Next ( 
   ULONG         celt,
   IDiaSegment** rgelt,
   ULONG*        pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 celt

から取得する列挙子内のセグメントの数。

 rgelt

入出力セグメントを表す目的の[IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)オブジェクトを使用して入力する配列。

 pceltFetched

入出力フェッチされた列挙子内のセグメントの数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 セグメントが存在しない場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)
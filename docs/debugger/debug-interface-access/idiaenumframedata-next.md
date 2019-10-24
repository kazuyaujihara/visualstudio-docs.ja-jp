---
title: 'IDiaEnumFrameData:: Next |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Next method
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6fe478e503ed6e16ee570f309f91434c658ebd27
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744599"
---
# <a name="idiaenumframedatanext"></a>IDiaEnumFrameData::Next
列挙シーケンス内の指定された数のフレームデータ要素を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Next ( 
   ULONG           celt,
   IDiaFrameData** rgelt,
   ULONG*          pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 celt

から取得する列挙子内のフレームデータ要素の数。

 rgelt

入出力要求されたフレームデータ要素を使用して入力される[IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)オブジェクトの配列。

 pceltFetched

入出力フェッチされた列挙子内のフレームデータ要素の数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 レコードがなくなった場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
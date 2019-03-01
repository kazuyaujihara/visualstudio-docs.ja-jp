---
title: Idiaenumstackframes::next |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumStackFrames::Next method
ms.assetid: 09378a21-d5e3-4213-b7e2-10f04d85295f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f9cf220c65cf11836e64a7e1f4c0142c89669f4b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56619447"
---
# <a name="idiaenumstackframesnext"></a>IDiaEnumStackFrames::Next
列挙体シーケンスから、指定したスタック フレームの要素数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Next( 
   ULONG             celt,
   IDiaStackFrame**  rgelt,
   ULONG*            pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 celt

[in]スタック フレームを取得する列挙子の要素の数。

 rgelt

[out]要求を格納する配列を[IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)オブジェクト。

 pceltFetched

[out]フェッチされた列挙子内のスタックのフレーム要素を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`スタック フレームがある場合。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
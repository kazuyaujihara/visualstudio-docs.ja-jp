---
title: 'IDiaEnumStackFrames:: Next |Microsoft Docs'
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
ms.openlocfilehash: ffde40e221823d9656c4b6414b14067ac9d0537a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744039"
---
# <a name="idiaenumstackframesnext"></a>IDiaEnumStackFrames::Next
列挙シーケンスから指定された数のスタックフレーム要素を取得します。

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

から取得する列挙子内のスタックフレーム要素の数。

 rgelt

入出力要求された[IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)オブジェクトを格納する配列。

 pceltFetched

入出力フェッチされた列挙子内のスタックフレーム要素の数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 スタックフレームがなくなった場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
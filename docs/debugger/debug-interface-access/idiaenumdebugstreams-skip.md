---
title: Idiaenumdebugstreams::skip |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams::Skip method
ms.assetid: 6ec7753c-d7af-4879-b107-1b3442e0b025
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 90bf6b41400143d7a6703db24c031cb3ed31de2c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838185"
---
# <a name="idiaenumdebugstreamsskip"></a>IDiaEnumDebugStreams::Skip
指定された数の列挙体シーケンス内の debug ストリームをスキップします。

## <a name="syntax"></a>構文

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>パラメーター
 `celt`

[in]スキップする列挙体シーケンス内の debug ストリームの数。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`をスキップするレコードがある場合。

## <a name="see-also"></a>関連項目
- [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)
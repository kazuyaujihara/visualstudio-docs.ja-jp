---
title: Idiaenumdebugstreamdata::next |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreamData::Next method
ms.assetid: 114171dd-38fd-4bd7-a702-8ff887ffc99b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cf641fde4c03053496c732aa7904ddcad671af20
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838608"
---
# <a name="idiaenumdebugstreamdatanext"></a>IDiaEnumDebugStreamData::Next
指定した列挙型のシーケンス内のレコード数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Next ( 
   ULONG  celt,
   DWORD  cbData,
   DWORD* pcbData,
   BYTE   data[],
   ULONG* pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 celt

[in]取得するレコードの数。

 cbData

[in]データバッファのサイズ（バイト単位）。

 pcbData

[out]返されるバイト数を返します。 場合`data`が null の場合、`pcbData`要求されたすべてのレコードの合計使用可能なデータのバイト数が含まれています。

 data[]

[out]デバッグ ストリーム レコードのデータを格納するバッファー。

 pceltFetched

[入力、出力]内のレコードの数を返します`data`します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`レコードがある場合。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
- [IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)
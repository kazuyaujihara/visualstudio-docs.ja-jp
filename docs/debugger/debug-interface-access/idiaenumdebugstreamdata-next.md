---
title: 'IDiaEnumDebugStreamData:: Next |Microsoft Docs'
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
ms.openlocfilehash: acdab0a565613194c67aa85484316a235c91dbf6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744789"
---
# <a name="idiaenumdebugstreamdatanext"></a>IDiaEnumDebugStreamData::Next
列挙されたシーケンス内の指定した数のレコードを取得します。

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

から取得するレコードの数。

 cbData

からデータバッファーのサイズ (バイト単位)。

 pcbData

入出力返されたバイト数を返します。 @No__t_0 が NULL の場合、`pcbData` には、要求されたすべてのレコードで使用可能なデータの合計バイト数が含まれます。

 data[]

入出力デバッグストリームレコードデータを格納するバッファー。

 pceltFetched

[入力、出力]@No__t_0 内のレコードの数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 レコードがなくなった場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
- [IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)
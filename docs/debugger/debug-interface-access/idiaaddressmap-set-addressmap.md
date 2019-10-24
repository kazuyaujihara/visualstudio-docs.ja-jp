---
title: IDiaAddressMap::set_addressMap | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8414788af44d78943088b78b2d3e42a5a8d8c50b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745029"
---
# <a name="idiaaddressmapset_addressmap"></a>IDiaAddressMap::set_addressMap
画像レイアウトの翻訳をサポートするアドレスマップを提供します。

## <a name="syntax"></a>構文

```C++
HRESULT set_addressMap ( 
   DWORD                     cbData,
   struct DiaAddressMapEntry data[],
   BOOL                      imagetoSymbols
);
```

#### <a name="parameters"></a>パラメーター
 `cbData`

から@No__t_0 パラメーター内の要素の数。

 `data[]`

から変換マップを定義する[DiaAddressMapEntry 構造](../../debugger/debug-interface-access/diaaddressmapentry.md)体の配列。

 `imagetoSymbols`

[in] `data` パラメーターが、デバッグシンボルによって記述されているように、新しいイメージレイアウトから元のレイアウトへのマップを定義する場合は `TRUE` します。 `data` が元のレイアウトから作成された新しいイメージレイアウトへのマップである場合に `FALSE` します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 通常、DIA は、プログラムデータベース (.pdb) ファイルからアドレス変換マップを取得します。 これらの値が欠落している場合は、 [IDiaAddressMap:: set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)メソッドが2回呼び出されます。1回は、`imagetoSymbols` パラメーターを `TRUE` に設定し、1回は `imagetoSymbols` パラメーターを `FALSE` に設定します。 両方の変換マップが指定されていない限り、 [IDiaAddressMap::P ut_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)メソッドを使用してアドレスマップの翻訳を有効にすることはできません。

## <a name="see-also"></a>関連項目
- [DiaAddressMapEntry 構造体](../../debugger/debug-interface-access/diaaddressmapentry.md)
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)
- [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)
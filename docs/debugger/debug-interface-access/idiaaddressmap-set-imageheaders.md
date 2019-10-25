---
title: IDiaAddressMap::set_imageHeaders | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ef17e1073c67ede75d075b18773129c287349c0d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745012"
---
# <a name="idiaaddressmapset_imageheaders"></a>IDiaAddressMap::set_imageHeaders
相対仮想アドレス変換を有効にするためにイメージヘッダーを設定します。

## <a name="syntax"></a>構文

```C++
HRESULT set_imageHeaders ( 
   DWORD cbData,
   BYTE  data[],
   BOOL  originalHeaders
);
```

#### <a name="parameters"></a>パラメーター
 cbData

からヘッダーデータのバイト数。 は `n*sizeof(IMAGE_SECTION_HEADER)` である必要があります。 `n` は実行可能ファイルのセクションヘッダーの数です。

 data[]

からイメージヘッダーとして使用される `IMAGE_SECTION_HEADER` 構造体の配列。

 originalHeaders

からイメージヘッダーが新しいイメージからのものである場合は `FALSE` に設定します。アップグレードの前に元のイメージが反映されている場合は `TRUE` します。 通常、これは、 [IDiaAddressMap:: set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)メソッドの呼び出しと組み合わせてのみ `TRUE` に設定されます。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 @No__t_0 構造体は、Winnt.h で宣言され、実行可能ファイルのイメージセクションヘッダー形式を表します。

 相対仮想アドレスの計算は、`IMAGE_SECTION_HEADER` の値によって異なります。 通常、DIA は、プログラムデータベース (.pdb) ファイルからこれらを取得します。 これらの値が指定されていない場合、DIA は相対仮想アドレスを計算できず、 [IDiaAddressMap:: get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)メソッドは `FALSE` を返します。 次に、クライアントは[IDiaAddressMap::P ut_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)メソッドを呼び出して、イメージ自体から不足しているイメージヘッダーを提供した後に、相対仮想アドレスの計算を有効にする必要があります。

## <a name="see-also"></a>関連項目
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
- [IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)
- [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)
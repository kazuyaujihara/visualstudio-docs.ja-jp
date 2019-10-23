---
title: IDiaAddressMap::put_addressMapEnabled | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_addressMapEnabled method
ms.assetid: 0f205337-4e59-4383-8059-7b1d207d6dcd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b5fe5589b667054ee75e3b01743553a2d60bef92
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745066"
---
# <a name="idiaaddressmapput_addressmapenabled"></a>IDiaAddressMap::put_addressMapEnabled
アドレスマップを使用してシンボルアドレスを変換する必要があるかどうかを指定します。

## <a name="syntax"></a>構文

```C++
HRESULT put_addressMapEnabled ( 
   BOOL NewVal
);
```

#### <a name="parameters"></a>パラメーター
 NewVal

からシンボルの変換を有効にする場合は `TRUE` に設定し、無効にする場合は `FALSE` に設定します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 実行可能なプロセッサの後で、実行可能ファイルが更新されることがあります。 DIA には、新しいレイアウトへのシンボルの変換をサポートする機構が含まれています。

 PDB ファイルが読み込まれると、ファイルに格納されているアドレスマップが有効になります。 ただし、クライアントアプリケーションで[IDiaAddressMap:: set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)メソッドを呼び出すことによって独自のアドレスマップを指定することが必要になる場合もあります。 @No__t_0 メソッドが正常に実行された場合、クライアントアプリケーションは、そのアドレスマップを使用できるように `TRUE` の `NewVal` パラメーターを使用して `put_addressMapEnabled` メソッドを呼び出す必要があります。

 有効になっているアドレスマップの現在の状態は、 [IDiaAddressMap:: get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)メソッドの呼び出しを使用して取得できます。

## <a name="see-also"></a>関連項目
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
- [IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)
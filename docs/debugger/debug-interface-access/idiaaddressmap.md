---
title: IDiaAddressMap | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap interface
ms.assetid: e6467529-508c-4328-85d7-89444ae4d1c1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7e06acf045ce1893762d5c898752dd6bc40de50a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744992"
---
# <a name="idiaaddressmap"></a>IDiaAddressMap
DIA SDK がデバッグオブジェクトの仮想および相対仮想アドレスを計算する方法を制御します。

## <a name="syntax"></a>構文

```
IDiaAddressMap : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、`IDiaAddressMap` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)|特定のセッションに対してアドレスマップが確立されているかどうかを示します。|
|[IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)|アドレスマップを使用してシンボルアドレスを変換する必要があるかどうかを指定します。|
|[IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)|計算と相対仮想アドレスの使用が有効かどうかを示します。|
|[IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)|クライアントが相対仮想アドレスの計算を有効または無効にすることを許可します。|
|[IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)|現在のイメージの配置を取得します。|
|[IDiaAddressMap::put_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)|イメージの配置を設定します。|
|[IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)|イメージヘッダーを設定して、相対仮想アドレスの変換を有効にします。|
|[IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)|画像レイアウトの翻訳をサポートするアドレスマップを提供します。|

## <a name="remarks"></a>Remarks
 このインターフェイスによって提供されるコントロールは、イメージヘッダーとアドレスマップという2つのデータセットにカプセル化されます。 ほとんどのクライアントでは、 [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドを使用してイメージの適切なデバッグ情報を検索します。メソッドは、通常、必要なすべてのヘッダーとマップデータを検出できます。 ただし、一部のクライアントは特殊な処理を実装し、データを検索します。 このようなクライアントは、`IDiaAddressMap` インターフェイスのメソッドを使用して、検索結果に DIA SDK を提供します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 このインターフェイスは、DIA session オブジェクトから入手できます。 クライアントは、DIA session オブジェクトインターフェイス (通常は[IDiaSession](../../debugger/debug-interface-access/idiasession.md)) で `QueryInterface` メソッドを呼び出して、`IDiaAddressMap` インターフェイスを取得します。

## <a name="requirements"></a>［要件］
 ヘッダー: Dia2

 ライブラリ: diaguids

 DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
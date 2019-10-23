---
title: 'IDiaAddressMap:: get_addressMapEnabled |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::get_addressMapEnabled method
ms.assetid: 6183dc5e-befa-4e5a-ae5a-f4aa24f3ed9e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b518cf3728279ea8db267d01867fa66ceae35b21
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745179"
---
# <a name="idiaaddressmapget_addressmapenabled"></a>IDiaAddressMap::get_addressMapEnabled
特定のセッションに対してアドレスマップが確立されているかどうかを示します。

## <a name="syntax"></a>構文

```C++
HRESULT get_addressMapEnabled ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 の場合は、

入出力アドレスマッピングが有効になっている場合は `TRUE` を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 実行可能なプロセッサの後で、実行可能ファイルが更新されることがあります。 DIA には、新しいレイアウトへのシンボルの変換をサポートする機構が含まれています。

 クライアントアプリケーションは、 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)インターフェイスから[IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)インターフェイスを取得し、 [IDiaAddressMap:: set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)メソッドを呼び出した後、その後にを呼び出すことによって、[特定のセッションのアドレスマップを設定できます。IDiaAddressMap::p ut_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)メソッド。 @No__t_0 メソッドは、`put_addressMapEnabled` メソッドを呼び出した結果を返します。

## <a name="see-also"></a>関連項目
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
- [IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)
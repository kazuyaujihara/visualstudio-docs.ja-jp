---
title: IDiaAddressMap::put_relativeVirtualAddressEnabled | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_relativeVirtualAddressEnabled method
ms.assetid: 767c078e-8ad7-4940-9e00-cae7704aadee
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1d733a51bd599b85dcc6d1121b8d21e1a687a351
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745036"
---
# <a name="idiaaddressmapput_relativevirtualaddressenabled"></a>IDiaAddressMap::put_relativeVirtualAddressEnabled
クライアントが相対仮想アドレス (RVA) の計算と使用を有効または無効にすることを許可します。

## <a name="syntax"></a>構文

```C++
HRESULT put_relativeVirtualAddressEnabled ( 
   BOOL NewVal
);
```

#### <a name="parameters"></a>パラメーター
 NewVal

からを `TRUE` に設定して、を有効にするか、`FALSE` を無効にします。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 DIA インターフェイスによって記述され、実行可能ファイルのイメージベースに対して相対的なデバッグオブジェクトのアドレスは、相対仮想アドレスとして取得できます。

 RVAs の使用は、セグメントが PDB ファイルから最初に読み込まれるときに有効になります。 RVAs の使用の現在の状態を取得するには、 [IDiaAddressMap:: get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)メソッドを呼び出します。

 RVAs メソッドを呼び出して、 [IDiaAddressMap:: set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)メソッドの呼び出しが正常に完了した後に、新しいイメージヘッダーが確立された後にを有効にする必要があります。 `put_relativeVirtualAddress`

## <a name="see-also"></a>関連項目
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)
- [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)
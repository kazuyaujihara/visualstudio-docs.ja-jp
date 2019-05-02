---
title: IDiaAddressMap::put_imageAlign | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_imageAlign method
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4e07bdd71300ed485862a4a95f1f9cbc06b32772
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63402649"
---
# <a name="idiaaddressmapputimagealign"></a>IDiaAddressMap::put_imageAlign
イメージの配置を設定します。

## <a name="syntax"></a>構文

```C++
HRESULT put_imageAlign ( 
   DWORD NewVal
);
```

#### <a name="parameters"></a>パラメーター
 NewVal

[in]実行可能ファイルの新しいイメージの配置の値。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 イメージ (読み込まれて実行可能ファイル) は、指定されたメモリ境界に揃えて配置されます。 この配置は、コンパイルとリンク時のオプションと現在のシステム アーキテクチャによって、影響を受けることができます。 イメージの配置は、バイト境界には常にします。 次のイメージの配置の値は有効です。1、2、4、8、16、32、および 64 バイトの境界。

 現在のイメージの配置への呼び出しで取得できる、 [idiaaddressmap::get_imagealign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)メソッド。

> [!NOTE]
> このメソッドを呼び出すことが時間によっては、イメージが既に読み込まれて。 `put_imageAlign`メソッドは通常新しい配置が必要ですし、イメージを移動または変更されている場合に使用します。

## <a name="see-also"></a>関連項目
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)
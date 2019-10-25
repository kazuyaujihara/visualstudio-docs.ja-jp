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
ms.openlocfilehash: 2b1a6bf037dc87d84fab21622571158fb0682f60
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745047"
---
# <a name="idiaaddressmapput_imagealign"></a>IDiaAddressMap::put_imageAlign
イメージの配置を設定します。

## <a name="syntax"></a>構文

```C++
HRESULT put_imageAlign ( 
   DWORD NewVal
);
```

#### <a name="parameters"></a>パラメーター
 NewVal

から実行可能ファイルの新しいイメージの配置値。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 イメージ (読み込まれた実行可能ファイル) は、指定されたメモリ境界に合わせて調整されます。 このアラインメントは、現在のシステムアーキテクチャと、コンパイルおよびリンク時のオプションによって影響を受ける可能性があります。 イメージの配置は、常にバイト境界上にあります。 次の画像の配置値は有効です: 1、2、4、8、16、32、および64バイト境界。

 現在のイメージの配置は、 [IDiaAddressMap:: get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)メソッドの呼び出しを使用して取得できます。

> [!NOTE]
> イメージは、このメソッドを呼び出すことができる時間によって既に読み込まれています。 @No__t_0 メソッドは、通常、イメージが移動または変更され、新しい配置が必要な場合に使用されます。

## <a name="see-also"></a>関連項目
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)
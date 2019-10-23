---
title: 'IDiaEnumFrameData:: フレーム Byva |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::frameByVA method
ms.assetid: 0b1e441b-710a-46d8-8060-bed39071c834
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9889a4f4add318209728bb09ac5c469c1fa836fe
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744644"
---
# <a name="idiaenumframedataframebyva"></a>IDiaEnumFrameData::frameByVA
仮想アドレス (VA) でフレームを返します。

## <a name="syntax"></a>構文

```C++
HRESULT frameByVA( 
   ULONGLONG       virtualAddress,
   IDiaFrameData** frame
);
```

#### <a name="parameters"></a>パラメーター
 virtualAddress

から目的のフレームの VA。

 フレーム

入出力指定されたアドレスを含むフレームを表す[IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 指定したアドレスと一致するフレームデータがない場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
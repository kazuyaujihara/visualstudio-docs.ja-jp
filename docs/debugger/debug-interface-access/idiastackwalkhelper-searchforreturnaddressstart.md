---
title: Idiastackwalkhelper::searchforreturnaddressstart |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper::searchForReturnAddressStart method
ms.assetid: 0a33142e-5d31-44ea-874a-a2e94d95cbd2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a311b10f2fc5b53daff58e93feec3a9cd6077d14
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56623347"
---
# <a name="idiastackwalkhelpersearchforreturnaddressstart"></a>IDiaStackWalkHelper::searchForReturnAddressStart
または、指定したスタック アドレスの近くのリターン アドレスの指定したスタック フレームを検索します。

## <a name="syntax"></a>構文

```C++
HRESULT searchForReturnAddressStart( 
   IDiaFrameData*  frame,
   ULONGLONG       startAddress,
   ULONGLONG*      returnAddress
);
```

#### <a name="parameters"></a>パラメーター
 `frame`

[in][IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)現在のスタック フレームを表すオブジェクト。

 `startAddress`

[in]元の検索を開始する仮想メモリ アドレス。

 `ReturnAddress`

[out]最も近い関数には、アドレスを返します`startAddress`します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
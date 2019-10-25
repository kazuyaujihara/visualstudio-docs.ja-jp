---
title: 'IDiaStackWalkHelper:: searchForReturnAddressStart |Microsoft Docs'
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
ms.openlocfilehash: b0753cfe2d9ef8b08606185a5f57a3951f54e7de
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741335"
---
# <a name="idiastackwalkhelpersearchforreturnaddressstart"></a>IDiaStackWalkHelper::searchForReturnAddressStart
指定したスタックフレーム内で、指定したスタックアドレス (またはその近く) の戻りアドレスを検索します。

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

から現在のスタックフレームを表す[IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)オブジェクト。

 `startAddress`

から検索を開始する仮想メモリアドレス。

 `ReturnAddress`

入出力@No__t_0 に最も近い関数の戻り先アドレスを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
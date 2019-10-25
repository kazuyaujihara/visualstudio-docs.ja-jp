---
title: 'IDiaStackWalkFrame:: searchForReturnAddressStart |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::searchForReturnAddressStart method
ms.assetid: 47660b9b-6e4f-4dfa-88ab-63dce28f7412
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7ad1c42a39b9c35cc1436488e19481f2b286b6f5
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741447"
---
# <a name="idiastackwalkframesearchforreturnaddressstart"></a>IDiaStackWalkFrame::searchForReturnAddressStart
指定したスタックフレーム内で、指定したアドレスまたはその近くの戻りアドレスを検索します。

## <a name="syntax"></a>構文

```C++
HRESULT searchForReturnAddressStart ( 
   IDiaFrameData* frame,
   ULONGLONG      startAddress,
   ULONGLONG*     returnAddress
);
```

#### <a name="parameters"></a>パラメーター
 `frame`

から現在のスタックフレームを表す[IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)オブジェクト。

 `startAddress`

から検索を開始する仮想メモリアドレス。

 `returnAddress`

入出力@No__t_0 に最も近い関数の戻り先アドレスを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
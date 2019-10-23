---
title: 'IDiaImageData:: get_relativeVirtualAddress |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_relativeVirtualAddress method
ms.assetid: e6d6deee-dc12-4b38-af15-f917b2d4368e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bfc7a808da6bb11907fc239f4b320e4dd93a2d19
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743426"
---
# <a name="idiaimagedataget_relativevirtualaddress"></a>IDiaImageData::get_relativeVirtualAddress
アプリケーションを基準として、モジュールの仮想メモリ内の場所を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_relativeVirtualAddress ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力モジュールの相対仮想メモリオフセットを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)
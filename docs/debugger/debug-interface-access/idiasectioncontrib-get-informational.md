---
title: Idiasectioncontrib::get_informational |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_informational method
ms.assetid: 5351e89f-7db1-4f8e-9e57-2dd1c74002e0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b00d07b788fe07fbe2e879f01a98929927743a0b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839590"
---
# <a name="idiasectioncontribgetinformational"></a>IDiaSectionContrib::get_informational
セクションには、コメント、または同様の情報が含まれるかどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_informational(
   BOOL* pRetVal
};
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します`TRUE`セクションには、コメント、またはその他の情報が含まれている場合を返しますそれ以外の場合`FALSE`します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 通常、.directive セクションには、情報が含まれています。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
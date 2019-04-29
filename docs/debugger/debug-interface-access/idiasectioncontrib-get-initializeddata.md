---
title: Idiasectioncontrib::get_initializeddata |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_initializedData method
ms.assetid: f5c108be-a0cc-408b-9590-b8d44361810c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ef878dcae9f8d6d29761bcda5f5aa9588f26d66c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62828160"
---
# <a name="idiasectioncontribgetinitializeddata"></a>IDiaSectionContrib::get_initializedData
セクションに初期化されたデータが含まれているかどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_initializedData ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します`TRUE`セクションには、初期化されたデータが含まれている場合を返しますそれ以外の場合、`FALSE`します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
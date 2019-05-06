---
title: Idiasectioncontrib::get_comdat |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_comdat method
ms.assetid: 8bd9be8d-59ee-4698-b055-daba354b8dcc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ddf479a2da74803916b7afc1945eb610d6b0e668
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62576634"
---
# <a name="idiasectioncontribgetcomdat"></a>IDiaSectionContrib::get_comdat
セクションは COMDAT レコードであるかどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_comdat ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します`TRUE`セクションが COMDAT レコード以外の場合を返しますそれ以外の場合、`FALSE`します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 COMDAT レコードとは、パッケージ化された関数をリンカーに表示する一般的なオブジェクト ファイル形式 (COFF) レコードです。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
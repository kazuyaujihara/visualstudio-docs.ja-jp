---
title: Idiaenumsectioncontribs::skip |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Skip method
ms.assetid: 7471a178-5134-41b2-80a6-51ff96abe916
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c90c2148fc5a563fef8946bd39acf4603d7d09f6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62833234"
---
# <a name="idiaenumsectioncontribsskip"></a>IDiaEnumSectionContribs::Skip
指定された数の列挙体シーケンスにおけるのセクションをスキップします。

## <a name="syntax"></a>構文

```C++
HRESULT Skip( 
   ULONG celt
);
```

#### <a name="parameters"></a>パラメーター
 `celt`

[in]スキップする列挙体シーケンス内のセクションの投稿の数。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`複数セクションをスキップする投稿がある場合。

## <a name="see-also"></a>関連項目
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)
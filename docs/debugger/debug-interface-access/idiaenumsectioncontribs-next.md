---
title: Idiaenumsectioncontribs::next |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Next method
ms.assetid: a6bb2adb-ee6d-4f3c-ab5b-e89361c8880e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8e8fd088ff6be619de56f27f91b198aed18e428c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62829785"
---
# <a name="idiaenumsectioncontribsnext"></a>IDiaEnumSectionContribs::Next
指定した列挙体シーケンス内のセクションの投稿数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Next( 
   ULONG                celt,
   IDiaSectionContrib** rgelt,
   ULONG*               pceltFetched
);
```

#### <a name="parameters"></a>パラメーター
 celt

[in]セクション多大な貢献を取得する列挙子の数。

 rgelt

[out]格納する配列、 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)セクションの目的の投稿物を表すオブジェクト。

 pceltFetched

[out]列挙子のフェッチにセクションの投稿物の数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`複数セクション投稿がある場合。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
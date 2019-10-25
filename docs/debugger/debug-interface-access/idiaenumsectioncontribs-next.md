---
title: 'IDiaEnumSectionContribs:: Next |Microsoft Docs'
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
ms.openlocfilehash: 61d99b0c881abdb8974e94352911ae3234c440c1
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744275"
---
# <a name="idiaenumsectioncontribsnext"></a>IDiaEnumSectionContribs::Next
列挙シーケンス内の指定された数のセクション投稿を取得します。

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

から取得する列挙子内のセクションの貢献数。

 rgelt

入出力目的のセクションの投稿を表す[IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)オブジェクトを格納する配列。

 pceltFetched

入出力フェッチされた列挙子内のセクションの貢献数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 セクションの投稿がこれ以上ない場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
---
title: Idiaenumtables::get_count |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::get_Count method
ms.assetid: 30fa316b-a746-4028-acae-4efcd2066f38
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e5cc51a166c5ac70c2db5358b893e52e2242d53
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56629756"
---
# <a name="idiaenumtablesgetcount"></a>IDiaEnumTables::get_Count
テーブルの数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_Count (    LONG* pRetVal
);

```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]テーブルの数を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
- [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)
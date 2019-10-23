---
title: 'IDiaEnumTables:: Clone |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Clone method
ms.assetid: beb21109-b12c-44d8-8c1f-a332216b3713
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 522ac4080331c869c32585dfed789378b1271542
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743790"
---
# <a name="idiaenumtablesclone"></a>IDiaEnumTables::Clone
現在の列挙子と同じ列挙状態を含む列挙子を作成します。

## <a name="syntax"></a>構文

```C++
HRESULT Clone ( 
   IDiaEnumTables** ppenum
);
```

#### <a name="parameters"></a>パラメーター
 `ppenum`

入出力列挙子の複製を含む[IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)オブジェクトを返します。 テーブルは重複しておらず、列挙子だけが複製されます。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
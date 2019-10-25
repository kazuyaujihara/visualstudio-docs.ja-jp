---
title: 'IDiaEnumLineNumbers:: Item |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9bba71efce68864b8737011ab7dda5cb8da3267c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744399"
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
インデックスを使って行番号を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item ( 
   DWORD            index,
   IDiaLineNumber** lineNumber
);
```

#### <a name="parameters"></a>パラメーター
 インデックス

から取得する[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)オブジェクトのインデックス。 インデックスは 0 ~ `count`-1 の範囲にあり、`count` は[IDiaEnumLineNumbers:: get_Count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md)メソッドによって返されます。

 lineNumber

入出力目的の行番号を表す[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
---
title: 'IDiaSession:: Getシンボル Byaddr |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::getSymbolsByAddr method
ms.assetid: eafcc757-b488-487d-a063-ad3703ff42e8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bfe5c047876b6e23c24ad850900cb0c66a4819d2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741900"
---
# <a name="idiasessiongetsymbolsbyaddr"></a>IDiaSession::getSymbolsByAddr
アドレスの順序で記号を検索する列挙子を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT getSymbolsByAddr( 
   IDiaEnumSymbolsByAddr** ppEnumbyAddr
);
```

#### <a name="parameters"></a>パラメーター
 `ppEnumbyAddr`

入出力[IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)オブジェクトを返します。 このインターフェイスを使用して、メモリ位置によってシンボルストア内のシンボルを検索します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)
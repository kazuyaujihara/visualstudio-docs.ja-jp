---
title: IDiaSession::findInlineeLinesByRVA |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7a74d5ee-0dbf-47c0-92b4-47ec03b13ce9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 900680fe58ab5061d3f8cca07fa1906cf34f7e5b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56642262"
---
# <a name="idiasessionfindinlineelinesbyrva"></a>IDiaSession::findInlineeLinesByRVA
により、クライアントは直接、インライン展開はすべての関数の直接的または間接的に指定した親シンボルの行番号情報を反復処理して、指定された相対仮想アドレス (RVA) 内に含まれる列挙体を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findInlineeLinesByRVA ( 
   IDiaSymbol*           parent,
   DWORD                 rva,
   DWORD                 length,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `parent`

[in]`IDiaSymbol`親を表すオブジェクト。

 `rva`

[in]として、RVA アドレスを指定します。

 `length`

[in]このクエリをカバーする、バイト数では、アドレスの範囲を指定します。

 `ppResult`

[out]保持する`IDiaEnumLineNumbers`取得される行番号の一覧を含むオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
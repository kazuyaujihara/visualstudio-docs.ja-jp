---
title: IDiaSymbol::findInlineeLinesByRVA |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ac108db1-9dbf-4dc4-bf48-159ca8d3725c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bdcb85db51a3fcfca434af9d39bc88587a0e5cdc
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "62831758"
---
# <a name="idiasymbolfindinlineelinesbyrva"></a>IDiaSymbol::findInlineeLinesByRVA
により、クライアントは、行番号の情報がインライン展開されて、直接または間接的に、指定された相対仮想アドレス (RVA) 内でこのシンボルのすべての関数を反復処理する列挙体を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findInlineeLinesByRVA (    DWORD                 rva,   DWORD                 length,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
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
- [IDiaSession::findInlineeLines](../../debugger/debug-interface-access/idiasession-findinlineelines.md)
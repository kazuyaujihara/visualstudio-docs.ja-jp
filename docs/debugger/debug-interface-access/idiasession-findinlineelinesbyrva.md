---
title: 'IDiaSession:: findInlineeLinesByRVA |Microsoft Docs'
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
ms.openlocfilehash: 6cf587d9e369ac32c72df5e1fd7a9005ef417177
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742207"
---
# <a name="idiasessionfindinlineelinesbyrva"></a>IDiaSession::findInlineeLinesByRVA
指定された親シンボルによって直接または間接的にインライン化され、指定された相対仮想アドレス (RVA) 内に含まれているすべての関数の行番号情報をクライアントが反復処理できるようにする列挙体を取得します。

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

から親を表す `IDiaSymbol` オブジェクト。

 `rva`

からアドレスを RVA として指定します。

 `length`

からこのクエリでカバーするアドレス範囲をバイト数で指定します。

 `ppResult`

入出力取得された行番号の一覧を含む `IDiaEnumLineNumbers` オブジェクトを保持します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
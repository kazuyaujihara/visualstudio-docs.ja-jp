---
title: IDiaSession::findInlineeLinesByAddr |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bb70e408-eed1-4c9c-b5b1-44323125f48b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a40cc8afdb60ad8ad76a0d6ee8e502a6a0b720b7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56622087"
---
# <a name="idiasessionfindinlineelinesbyaddr"></a>IDiaSession::findInlineeLinesByAddr
により、クライアントは直接、インライン展開はすべての関数の直接的または間接的に指定した親シンボルの行番号情報を反復処理して、指定したアドレスの範囲内に含まれる列挙体を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findInlineeLinesByAddr ( 
   IDiaSymbol*           parent,   DWORD                 isect,   DWORD                 offset,   DWORD                 length,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `parent`

[in]`IDiaSymbol`親を表すオブジェクト。

 `isect`

[in]アドレスのセクションのコンポーネントを指定します。

 `offset`

[in]アドレスのオフセットのコンポーネントを指定します。

 `length`

[in]このクエリをカバーする、バイト数では、アドレスの範囲を指定します。

 `ppResult`

[out]保持する`IDiaEnumLineNumbers`取得される行番号の一覧を含むオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>参照
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
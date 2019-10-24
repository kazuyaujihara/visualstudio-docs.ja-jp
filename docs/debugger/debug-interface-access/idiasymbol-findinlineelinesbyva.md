---
title: 'IDiaSymbol:: findInlineeLinesByVA |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 61427d33-30d2-4ac9-9bd6-c58c6c705072
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de092109282506747606799b45b89059bf41fd8a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741197"
---
# <a name="idiasymbolfindinlineelinesbyva"></a>IDiaSymbol::findInlineeLinesByVA
指定した仮想アドレス (VA) 内のこのシンボルに直接または間接的にインライン化されているすべての関数の行番号情報をクライアントが反復処理できるようにする列挙体を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findInlineeLinesByVA ( 
   ULONGLONG             va,
   DWORD                 length,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `va`

からアドレスを VA として指定します。

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
---
title: 'IDiaSession:: findInlineeLinesByLinenum |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fe238f3bc66d6a7c5978c5d7cbebcd185fcd43d2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742223"
---
# <a name="idiasessionfindinlineelinesbylinenum"></a>IDiaSession::findInlineeLinesByLinenum
指定したソースファイルと行番号で、直接または間接的にインライン化されているすべての関数の行番号情報をクライアントが反復処理できるようにする列挙体を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findInlineeLinesByVA ( 
   IDiaSymbol*           compiland,
   IDiaSourceFile*       file,
   DWORD                 linenum,
   DWORD                 column,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `compiland`

から行番号を検索するコンパイル単位を表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクト。 このパラメーターを `NULL` とすることはできません。

 `file`

から検索するソースファイルを表す[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)オブジェクト。 このパラメーターを `NULL` とすることはできません。

 `linenum`

から1から始まる行番号を指定します。

> [!NOTE]
> 0を使用してすべての行を指定することはできません (すべての行を検索するには、 [IDiaSession:: findlines](../../debugger/debug-interface-access/idiasession-findlines.md)メソッドを使用します)。

 `column`

から列番号を指定します。 すべての列を指定するには0を使用します。 列は、1行に対するバイトオフセットです。

 `ppResult`

入出力取得された行番号の一覧を含む[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
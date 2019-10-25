---
title: 'IDiaSession:: Findinlineline|Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b6822d8b-70d5-470b-8278-3aec4680326c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5103a881b1b046479a1a3156f06038e230f5063e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742241"
---
# <a name="idiasessionfindinlineelines"></a>IDiaSession::findInlineeLines
指定した親シンボルによってインラインで、直接または間接的にインライン化されているすべての関数の行番号情報をクライアントが反復処理できるようにする列挙体を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findInlineeLines ( 
   IDiaSymbol*       parent,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `parent`

から親を表す `IDiaSymbol` オブジェクト。

 `ppResult`

入出力取得された行番号の一覧を含む `IDiaEnumLineNumbers` オブジェクトを保持します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
---
title: 'IDiaSession:: findInlineeLinesByAddr |Microsoft Docs'
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
ms.openlocfilehash: 496f6b569b3ac02c625ddf18406b78fdb1687be2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742236"
---
# <a name="idiasessionfindinlineelinesbyaddr"></a>IDiaSession::findInlineeLinesByAddr
クライアントが、指定された親シンボルによって直接または間接的にインライン化されているすべての関数の行番号情報を反復処理できるようにする列挙体を取得します。指定したアドレス範囲内に含まれます。

## <a name="syntax"></a>構文

```C++
HRESULT findInlineeLinesByAddr ( 
   IDiaSymbol*           parent,   DWORD                 isect,   DWORD                 offset,   DWORD                 length,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `parent`

から親を表す `IDiaSymbol` オブジェクト。

 `isect`

からアドレスのセクション部分を指定します。

 `offset`

からアドレスのオフセットコンポーネントを指定します。

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
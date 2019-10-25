---
title: 'IDiaSession:: findAcceleratorInlineesByLinenum |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 386c87aa-f7b2-4d38-9dd6-fffba9ff01f0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6d08168a83b9bb635fd6a0e22dc22f91a454001f
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742320"
---
# <a name="idiasessionfindacceleratorinlineesbylinenum"></a>IDiaSession::findAcceleratorInlineesByLinenum
指定したソースの場所に対応するインラインフレームのシンボルの列挙体を返します。

## <a name="syntax"></a>構文

```C++
HRESULT findAcceleratorInlineeLinesByName ( 
   IDiaSymbol*           parent,
   IDiaSourceFile*       file,
   DWORD                 linenum,
   DWORD                 colnum,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `parent`

から検索する必要があるアクセラレータのスタブ関数に対応する `IDiaSymbol`。

 `file`

からソースの場所の `IDiaSourceFile`。

 `linenum`

からソースの場所の行番号。

 `colnum`

からソースの場所の列番号。

 `ppResult`

入出力結果を使用して初期化される `IDiaEnumLineNumbers` インターフェイスポインターへのポインター。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
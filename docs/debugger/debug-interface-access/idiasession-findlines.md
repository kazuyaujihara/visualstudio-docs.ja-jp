---
title: 'IDiaSession:: findLines |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLines method
ms.assetid: d6e84916-fd55-457e-b057-57f97b51fe73
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d6082bfe8a3eee00d425441ff44a6eadd1c36e27
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742122"
---
# <a name="idiasessionfindlines"></a>IDiaSession::findLines
指定されたコンパイル単位とソースファイルの識別子内の行番号を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findLines ( 
   IDiaSymbol*           compiland,
   IDiaSourceFile*       file,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `compiland`

からコンパイル単位を表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクト。 このインターフェイスは、行番号を検索するコンテキストとして使用します。

 `file`

から行番号を検索するソースファイルを表す[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)オブジェクト。

 `ppResult`

入出力取得した行番号の一覧を含む[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
---
title: Idiasession::findlines |Microsoft Docs
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
ms.openlocfilehash: b127cbc5c9ddc5a2aa2d293d1371bab18d191fdb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839291"
---
# <a name="idiasessionfindlines"></a>IDiaSession::findLines
指定したコンパイル単位とソース ファイル識別子内で行番号を取得します。

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

[in][IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)コンパイル単位を表すオブジェクト。 行番号を検索するためのコンテキストとしては、このインターフェイスを使用します。

 `file`

[in][IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)で行番号を検索するソース ファイルを表すオブジェクト。

 `ppResult`

[out]返します、 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)行番号の一覧を含むオブジェクトを取得します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
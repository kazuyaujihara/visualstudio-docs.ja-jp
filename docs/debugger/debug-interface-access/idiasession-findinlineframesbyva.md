---
title: 'IDiaSession:: findInlineFramesByVA |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: df9e68f6-e0a4-4cf6-b11d-61c40351e0cd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dca26021909220f9bb68a6794c299ec6c5a3d75a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742141"
---
# <a name="idiasessionfindinlineframesbyva"></a>IDiaSession::findInlineFramesByVA
指定された仮想アドレス (VA) 上のすべてのインラインフレームをクライアントが反復処理できるようにする列挙を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findInlineFramesByVA ( 
   IDiaSymbol*       parent,   ULONGLONG         va,
   IDiaEnumSymbols** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `parent`

から親を表す `IDiaSymbol` オブジェクト。

 `va`

からアドレスを VA として指定します。

 `ppResult`

入出力取得されたフレームの一覧を含む `IDiaEnumSymbols` オブジェクトを保持します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
---
title: 'IDiaSession:: Find Byva |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByVA method
ms.assetid: f647eee9-a73c-483b-9fe9-21f42e560a7b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2513825fd2b6f4e6035f9f23295f0c9f00385d0a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742069"
---
# <a name="idiasessionfindlinesbyva"></a>IDiaSession::findLinesByVA
指定した仮想アドレス (VA) 範囲に含まれる行の行番号情報を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findLinesByVA (
    ULONGLONG             va,
    DWORD                 length,
    IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
`va`

からアドレスを VA として指定します。

`length`

からこのクエリでカバーするアドレス範囲のバイト数を指定します。

`ppResult`

入出力指定されたアドレス範囲に対応するすべての行番号のリストを含む[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)オブジェクトを返します。

## <a name="example"></a>例
この例は、関数の仮想アドレスと長さを使用して、関数に含まれるすべての行番号を取得する関数を示しています。

```C++
IDiaEnumLineNumbers *GetLineNumbersByVA(IDiaSymbol *pFunc, IDiaSession *pSession)
{
    IDiaEnumLineNumbers* pEnum = NULL;
    ULONGLONG            va;
    ULONGLONG            length;

    if (pFunc->get_virtualAddress ( &va ) == S_OK)
    {
        pFunc->get_length( &length );
        pSession->findLinesByVA( va, static_cast<DWORD>( length ), &pEnum );
    }
    return(pEnum);
}
```

## <a name="see-also"></a>関連項目
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)

---
title: 'IDiaSession:: Find Byrva |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByRVA method
ms.assetid: 06f53b0b-b5b4-42cf-9252-dcee0dbe2d71
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b6dfe92a5c804c0c81bfff6fa457e1ca797a62f9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742087"
---
# <a name="idiasessionfindlinesbyrva"></a>IDiaSession::findLinesByRVA
指定された相対仮想アドレス (RVA) を含む、指定されたコンパイル単位内の行を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findLinesByRVA ( 
    DWORD                 rva,
    DWORD                 length,
    IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
`rva`

からアドレスを RVA として指定します。

`length`

からこのクエリでカバーするアドレス範囲のバイト数を指定します。

`ppResult`

入出力指定されたアドレス範囲に対応するすべての行番号のリストを含む[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="example"></a>例
この例は、関数の相対仮想アドレスと長さを使用して、指定された関数に含まれるすべての行番号を取得する関数を示しています。

```C++
IDiaEnumLineNumbers* GetLineNumbersByRVA(IDiaSymbol *pFunc, IDiaSession *pSession)
{
    IDiaEnumLineNumbers* pEnum = NULL;
    DWORD                rva;
    ULONGLONG            length;

    if (pFunc->get_relativeVirtualAddress ( &rva ) == S_OK)
    {
        pFunc->get_length ( &length );
        pSession->findLinesByRVA( rva, static_cast<DWORD>( length ), &pEnum );
    }
    return(pEnum);
}
```

## <a name="see-also"></a>関連項目
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)

---
title: 'IDiaSession:: Find、Byaddr |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByAddr method
ms.assetid: 640403c0-14cf-403c-ad19-38b3bdc28ca8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 328589df0e662ca27db634017005344d44491275
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742120"
---
# <a name="idiasessionfindlinesbyaddr"></a>IDiaSession::findLinesByAddr
指定したアドレスを含む、指定したコンパイル単位内の行を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findLinesByAddr (
    DWORD                 seg,
    DWORD                 offset,
    DWORD                 length,
    IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
`seg`

から特定のアドレスのセクション部分を指定します。

`offset`

から特定のアドレスのオフセットコンポーネントを指定します。

`length`

からこのクエリでカバーするアドレス範囲のバイト数を指定します。

`ppResult`

入出力指定されたアドレス範囲に対応するすべての行番号のリストを含む[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="example"></a>例
この例は、関数のアドレスと長さを使用して、関数に含まれるすべての行番号を取得する関数を示しています。

```C++
IDiaEnumLineNumbers* GetLineNumbersByAddr(IDiaSymbol *pFunc,
                                          IDiaSession *pSession)
{
    IDiaEnumLineNumbers* pEnum = NULL;
    DWORD                seg;
    DWORD                offset;
    ULONGLONG            length;

    if (pFunc->get_addressSection ( &seg ) == S_OK &&
        pFunc->get_addressOffset ( &offset ) == S_OK)
    {
        pFunc->get_length ( &length );
        pSession->findLinesByAddr( seg, offset, static_cast<DWORD>( length ), &pEnum );
    }
    return(pEnum);
}
```

## <a name="see-also"></a>関連項目
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSession::findLinesByVA](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)

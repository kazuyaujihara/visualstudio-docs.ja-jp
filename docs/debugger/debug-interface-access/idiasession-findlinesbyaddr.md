---
title: Idiasession::findlinesbyaddr |Microsoft Docs
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
ms.openlocfilehash: 57ef75b27f90df37132ecb246b6f8d433581a696
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227460"
---
# <a name="idiasessionfindlinesbyaddr"></a>IDiaSession::findLinesByAddr
指定したコンパイル単位で指定されたアドレスが含まれている行を取得します。

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
[in]特定のアドレスのセクションのコンポーネントを指定します。

`offset`  
[in]特定のアドレスのオフセットのコンポーネントを指定します。

`length`  
[in]このクエリをカバーするアドレス範囲のバイト数を指定します。

`ppResult`  
[out]返します、 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)番号ものを対象指定されたアドレス範囲のすべての行のリストを含むオブジェクト。

## <a name="return-value"></a>戻り値
成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="example"></a>例
この例では、関数のアドレスと長さを使用して関数に含まれるすべての行番号を取得する関数を使用します。

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

## <a name="see-also"></a>参照
[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)  
[IDiaSession](../../debugger/debug-interface-access/idiasession.md)  
[IDiaSession::findLinesByVA](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)

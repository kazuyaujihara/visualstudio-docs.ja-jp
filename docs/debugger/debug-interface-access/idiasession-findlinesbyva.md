---
title: Idiasession::findlinesbyva |Microsoft Docs
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
ms.openlocfilehash: 29f3f714cdcbe529dac98948f6568934a6f508af
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56646826"
---
# <a name="idiasessionfindlinesbyva"></a>IDiaSession::findLinesByVA
指定された仮想アドレス (VA) の範囲内に含まれる行の行番号情報を取得します。

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

[in]として、問い合わせください。 アドレスを指定します。

`length`

[in]このクエリをカバーするアドレス範囲のバイト数を指定します。

`ppResult`

[out]返します、 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)番号ものを対象指定されたアドレス範囲のすべての行のリストを含むオブジェクト。

## <a name="example"></a>例
この例では、関数の仮想アドレスと長さを使用して関数に含まれるすべての行番号を取得する関数を使用します。

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

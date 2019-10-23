---
title: IDiaSession::symbolById | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symbolById method
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b0ffcb6c438150bff82f17a66c3347c300b17d72
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741875"
---
# <a name="idiasessionsymbolbyid"></a>IDiaSession::symbolById
一意の識別子によって記号を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT symbolById (
    DWORD        id,
    IDiaSymbol** ppSymbol
);
```

#### <a name="parameters"></a>パラメーター
`id`

から一意の識別子。

`ppSymbol`

入出力取得されたシンボルを表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
指定された識別子は、すべての記号を一意にするために DIA SDK によって内部的に使用される一意の値です。

たとえば、このメソッドを使用すると、別のシンボルの型を表すシンボルを取得できます (例を参照)。

## <a name="example"></a>例
この例では、別のシンボルの型を表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)を取得します。 この例では、セッションで `symbolById` メソッドを使用する方法を示します。 より簡単な方法は、 [IDiaSymbol:: get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)メソッドを呼び出して、型シンボルを直接取得することです。

```C++
IDiaSymbol *GetSymbolType(IDiaSymbol *pSymbol, IDiaSession *pSession)
{
    IDiaSymbol *pTypeSymbol = NULL;
    if (pSymbol != NULL && pSession != NULL)
    {
        DWORD symbolTypeId;
        pSymbol->get_typeId(&symbolTypeId);
        pSession->symbolById(symbolTypeId, &pTypeSymbol);
    }
    return(pTypeSymbol);
}
```

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)

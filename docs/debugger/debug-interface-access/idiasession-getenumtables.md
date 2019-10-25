---
title: 'IDiaSession:: getEnumTables |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::getEnumTables method
ms.assetid: 66e0fba2-ca63-4e24-a46a-c99c7fb61dd1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41679304986f5de948119a2958524b8f269ceb42
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741919"
---
# <a name="idiasessiongetenumtables"></a>IDiaSession::getEnumTables
シンボルストアに格納されているすべてのテーブルの列挙子を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT getEnumTables (
    IDiaEnumTables** ppEnumTables
);
```

#### <a name="parameters"></a>パラメーター
`ppEnumTables`

入出力[IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)オブジェクトを返します。 このインターフェイスを使用して、シンボルストア内のテーブルを列挙します。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="example"></a>例
この例では、`getEnumTables` メソッドを使用して特定の列挙子オブジェクトを取得する一般的な関数を示します。 列挙子が見つかった場合、関数は、目的のインターフェイスにキャストできるポインターを返します。それ以外の場合、関数は `NULL` を返します。

```C++
IUnknown *GetTable(IDiaSession *pSession, REFIID iid)
{
    IUnknown *pUnknown = NULL;
    if (pSession != NULL)
    {
        CComPtr<IDiaEnumTables> pEnumTables;
        if (pSession->getEnumTables(&pEnumTables) == S_OK)
        {
            CComPtr<IDiaTable> pTable;
            DWORD celt = 0;
            while(pEnumTables->Next(1,&pTable,&celt) == S_OK &&
                  celt == 1)
            {
                if (pTable->QueryInterface(iid, (void **)pUnknown) == S_OK)
                {
                    break;
                }
                pTable = NULL;
            }
        }
    }
    return(pUnknown);
}
```

## <a name="see-also"></a>関連項目
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)

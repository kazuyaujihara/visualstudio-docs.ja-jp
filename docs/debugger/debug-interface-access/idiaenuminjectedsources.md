---
title: IDiaEnumInjectedSources |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources interface
ms.assetid: f97e2392-22e1-48da-b7ce-ad94c8b684b0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: feaf5d372279c6ab24053058a14aba4b3a71fd78
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744473"
---
# <a name="idiaenuminjectedsources"></a>IDiaEnumInjectedSources
データソースに格納されている、挿入されたさまざまなソースを列挙します。

## <a name="syntax"></a>構文

```
IDiaEnumInjectedSources : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、`IDiaEnumInjectedSources` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaEnumInjectedSources::get__NewEnum](../../debugger/debug-interface-access/idiaenuminjectedsources-get-newenum.md)|この列挙子の[IEnumVARIANT インターフェイス](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ienumvariant)バージョンを取得します。|
|[IDiaEnumInjectedSources::get_Count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md)|挿入されたソースの数を取得します。|
|[IDiaEnumInjectedSources::Item](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md)|インデックスを使って挿入されたソースを取得します。|
|[IDiaEnumInjectedSources::Next](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md)|列挙シーケンス内の指定した数の挿入されたソースを取得します。|
|[IDiaEnumInjectedSources::Skip](../../debugger/debug-interface-access/idiaenuminjectedsources-skip.md)|列挙シーケンス内の、指定した数の挿入されたソースをスキップします。|
|[IDiaEnumInjectedSources::Reset](../../debugger/debug-interface-access/idiaenuminjectedsources-reset.md)|列挙シーケンスを先頭にリセットします。|
|[IDiaEnumInjectedSources::Clone](../../debugger/debug-interface-access/idiaenuminjectedsources-clone.md)|現在の列挙子と同じ列挙状態を含む列挙子を作成します。|

## <a name="remarks"></a>Remarks

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
このインターフェイスは、特定のソースファイルの名前を指定して[IDiaSession:: findInjectedSource](../../debugger/debug-interface-access/idiasession-findinjectedsource.md)メソッドを呼び出すか、または `IDiaEnumInjectedSources` インターフェイスの GUID で[IDiaSession:: getenumtables](../../debugger/debug-interface-access/idiasession-getenumtables.md)メソッドを呼び出すことによって取得されます。

## <a name="example"></a>例
この例では、(`GetEnumInjectedSources` 関数) を取得し、`IDiaEnumInjectedSources` インターフェイスで (`DumpAllInjectedSources` 関数) を使用する方法を示します。 @No__t_1 関数の実装については、 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)インターフェイスを参照してください。 別の出力については、「 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)インターフェイス」を参照してください。

```C++

IDiaEnumInjectedSources* GetEnumInjectedSources(IDiaSession *pSession)
{
    IDiaEnumInjectedSources* pUnknown    = NULL;
    REFIID                   iid         = __uuidof(IDiaEnumInjectedSources);
    IDiaEnumTables*          pEnumTables = NULL;
    IDiaTable*               pTable      = NULL;
    ULONG                    celt        = 0;

    if (pSession->getEnumTables(&pEnumTables) != S_OK)
    {
        wprintf(L"ERROR - GetTable() getEnumTables\n");
        return NULL;
    }
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)
    {
        // There is only one table that matches the given iid
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);
        pTable->Release();
        if (hr == S_OK)
        {
            break;
        }
    }
    pEnumTables->Release();
    return pUnknown;
}

void DumpAllInjectedSources( IDiaSession* pSession)
{
    IDiaEnumInjectedSources* pEnumInjSources;

    pEnumInjSources = GetEnumInjectedSources(pSession);
    if (pEnumInjSources != NULL)
    {
        IDiaInjectedSource* pInjSource;
        ULONG celt = 0;

        while(pEnumInjSources->Next(1, &pInjSource, &celt) == S_OK &&
              celt == 1)
        {
            IDiaPropertyStorage *pPropertyStorage;
            if (pInjSource->QueryInterface(__uuidof(IDiaPropertyStorage),
                                          (void **)&pPropertyStorage) == S_OK)
            {
                PrintPropertyStorage(pPropertyStorage);
                pPropertyStorage->Release();
            }
            pInjSource->Release();
        }
        pEnumInjSources->Release();
    }
}
```

## <a name="requirements"></a>［要件］
ヘッダー: Dia2

ライブラリ: diaguids

DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaSession::findInjectedSource](../../debugger/debug-interface-access/idiasession-findinjectedsource.md)
- [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
- [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)

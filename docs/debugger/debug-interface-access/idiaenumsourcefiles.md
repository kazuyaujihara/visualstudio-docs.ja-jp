---
title: IDiaEnumSourceFiles |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles interface
ms.assetid: 5c0779a6-a2ea-408a-90da-ebdecf2b83c0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 091d2f5996d53341e57c5c1b2125609642a156eb
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744028"
---
# <a name="idiaenumsourcefiles"></a>IDiaEnumSourceFiles
データソースに格納されているさまざまなソースファイルを列挙します。

## <a name="syntax"></a>構文

```
IDiaEnumSourceFiles : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、`IDiaEnumSourceFiles` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaEnumSourceFiles::get__NewEnum](../../debugger/debug-interface-access/idiaenumsourcefiles-get-newenum.md)|この列挙子の `IEnumVARIANT Interface` バージョンを取得します。|
|[IDiaEnumSourceFiles::get_Count](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md)|ソースファイルの数を取得します。|
|[IDiaEnumSourceFiles::Item](../../debugger/debug-interface-access/idiaenumsourcefiles-item.md)|インデックスを使ってソースファイルを取得します。|
|[IDiaEnumSourceFiles::Next](../../debugger/debug-interface-access/idiaenumsourcefiles-next.md)|列挙シーケンス内の指定された数のソースファイルを取得します。|
|[IDiaEnumSourceFiles::Skip](../../debugger/debug-interface-access/idiaenumsourcefiles-skip.md)|列挙シーケンス内の指定された数のソースファイルをスキップします。|
|[IDiaEnumSourceFiles::Reset](../../debugger/debug-interface-access/idiaenumsourcefiles-reset.md)|列挙シーケンスを先頭にリセットします。|
|[IDiaEnumSourceFiles::Clon](../../debugger/debug-interface-access/idiaenumsourcefiles-clone.md)|現在の列挙子と同じ列挙状態を含む列挙子を作成します。|

## <a name="remarks"></a>Remarks

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
このインターフェイスを取得するには、 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)オブジェクトの `QueryInterface` メソッドを呼び出します。 詳細については、例を参照してください。

## <a name="example"></a>例
この例では、DIA session オブジェクトのテーブルの一覧から `IDiaEnumSourceFiles` インターフェイスを取得する方法を示します。 ソースファイルの情報にアクセスする例については、 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)インターフェイスを参照してください。

```C++

IDiaEnumSourceFiles* GetEnumSourceFiles(IDiaSession *pSession)
{
    IDiaEnumSourceFiles * pUnknown    = NULL;
    REFIID                iid         = __uuidof(IDiaEnumSourceFiles);
    IDiaEnumTables*       pEnumTables = NULL;
    IDiaTable*            pTable      = NULL;
    ULONG                 celt        = 0;

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
```

## <a name="requirements"></a>［要件］
ヘッダー: Dia2

ライブラリ: diaguids

DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)
- [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)

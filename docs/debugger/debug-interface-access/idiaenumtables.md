---
title: IDiaEnumTables |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables interface
ms.assetid: 016190c5-09e4-48f2-bf60-9b02603a03e0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d505219468f802a3eff9df0ad766fd1a353d5166
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743697"
---
# <a name="idiaenumtables"></a>IDiaEnumTables
データソースに格納されているさまざまなテーブルを列挙します。

## <a name="syntax"></a>構文

```
IDiaEnumTables : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、`IDiaEnumTables` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaEnumTables::get__NewEnum](../../debugger/debug-interface-access/idiaenumtables-get-newenum.md)|この列挙子の[IEnumVARIANT インターフェイス](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ienumvariant)バージョンを取得します。|
|[IDiaEnumTables::get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)|テーブルの数を取得します。|
|[IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)|インデックスまたは名前を使ってテーブルを取得します。|
|[IDiaEnumTables::Next](../../debugger/debug-interface-access/idiaenumtables-next.md)|列挙シーケンス内の指定された数のテーブルを取得します。|
|[IDiaEnumTables::Skip](../../debugger/debug-interface-access/idiaenumtables-skip.md)|列挙シーケンス内の指定された数のテーブルをスキップします。|
|[IDiaEnumTables::Reset](../../debugger/debug-interface-access/idiaenumtables-reset.md)|列挙シーケンスを先頭にリセットします。|
|[IDiaEnumTables::Clone](../../debugger/debug-interface-access/idiaenumtables-clone.md)|現在の列挙子と同じ列挙状態を含む列挙子を作成します。|

## <a name="remarks"></a>Remarks

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
このインターフェイスを取得するには、 [IDiaSession:: getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)メソッドを呼び出します。

## <a name="example"></a>例
この例では、セッションから `IDiaEnumTables` インターフェイスを取得する方法を示します。 テーブルを使用する詳細な例については、 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)インターフェイスを参照してください。

```C++
void ShowTableNames(IDiaSession *pSession)
{
    CComPtr<IDiaEnumTables> pTables;
    if ( FAILED( psession->getEnumTables( &pTables ) ) )
    {
        Fatal( "getEnumTables" );
    }
    // Do something with table
}
```

## <a name="requirements"></a>［要件］
ヘッダー: Dia2

ライブラリ: diaguids

DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)

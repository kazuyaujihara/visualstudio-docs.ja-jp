---
title: IDiaEnumDebugStreams |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams interface
ms.assetid: 611caf4f-7a5f-4aa4-b909-52feeb3cc752
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 70e14e594b385a2fa93f51eed4dec36d74db347e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744690"
---
# <a name="idiaenumdebugstreams"></a>IDiaEnumDebugStreams
データソースに格納されているさまざまなデバッグストリームを列挙します。

## <a name="syntax"></a>構文

```
IDiaEnumDebugStreams : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、`IDiaEnumDebugStreams` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaEnumDebugStreams::get__NewEnum](../../debugger/debug-interface-access/idiaenumdebugstreams-get-newenum.md)|この列挙子の `IEnumVARIANT` バージョンを取得します。|
|[IDiaEnumDebugStreams::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreams-get-count.md)|デバッグストリームの数を取得します。|
|[IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)|インデックスを使ってデバッグストリームを取得します。|
|[IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)|列挙シーケンス内の指定された数のデバッグストリームを取得します。|
|[IDiaEnumDebugStreams::Skip](../../debugger/debug-interface-access/idiaenumdebugstreams-skip.md)|列挙シーケンス内の指定された数のデバッグストリームをスキップします。|
|[IDiaEnumDebugStreams::Reset](../../debugger/debug-interface-access/idiaenumdebugstreams-reset.md)|列挙シーケンスを先頭にリセットします。|
|[IDiaEnumDebugStreams::Clone](../../debugger/debug-interface-access/idiaenumdebugstreams-clone.md)|現在の列挙子と同じ列挙状態を含む列挙子を作成します。|

## <a name="remarks"></a>Remarks
デバッグストリームの内容は実装に依存し、データ形式は文書化されていません。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
[IDiaSession:: getEnumDebugStreams](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md)メソッドを呼び出して、`IDiaEnumDebugStreams` オブジェクトを取得します。

## <a name="example"></a>例
この例では、このインターフェイスから使用可能なデータストリームにアクセスする方法を示します。 @No__t_1 関数の実装については、 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)インターフェイスを参照してください。

```C++
void DumpAllDebugStreams( IDiaSession* pSession)
{
    IDiaEnumDebugStreams* pEnumStreams;

    wprintf(L"\n\n*** DEBUG STREAMS\n\n");
    // Retrieve an enumerated sequence of debug data streams
    if(pSession->getEnumDebugStreams(&pEnumStreams) == S_OK)
    {
        IDiaEnumDebugStreamData* pStream;
        ULONG celt = 0;

        for(; pEnumStreams->Next(1, &pStream, &celt) == S_OK; pStream = NULL)
        {
            PrintStreamData(pStream);
            pStream->Release();
        }
        pEnumStreams->Release();
    }
    else
    {
        wprintf(L"Failed to get any debug streams!\n");
    }
    wprintf(L"\n");
}
```

## <a name="requirements"></a>［要件］
ヘッダー: Dia2

ライブラリ: diaguids

DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
- [IDiaSession::getEnumDebugStreams](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md)

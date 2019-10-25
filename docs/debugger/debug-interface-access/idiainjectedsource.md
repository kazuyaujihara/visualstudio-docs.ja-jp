---
title: IDiaInjectedSource |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource interface
ms.assetid: 75192c5c-812d-4675-9dc5-4c2cff3ba503
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 994f454372883f2516d1eab03bf1152693969b16
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743304"
---
# <a name="idiainjectedsource"></a>IDiaInjectedSource
DIA データソースに格納されている挿入されたソースコードにアクセスします。

## <a name="syntax"></a>構文

```
IDiaInjectedSource : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、`IDiaInjectedSource` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaInjectedSource::get_crc](../../debugger/debug-interface-access/idiainjectedsource-get-crc.md)|ソースコードのバイトから計算された巡回冗長検査 (CRC) を取得します。|
|[IDiaInjectedSource::get_length](../../debugger/debug-interface-access/idiainjectedsource-get-length.md)|コードのバイト数を取得します。|
|[IDiaInjectedSource::get_filename](../../debugger/debug-interface-access/idiainjectedsource-get-filename.md)|ソースのファイル名を取得します。|
|[IDiaInjectedSource::get_objectFilename](../../debugger/debug-interface-access/idiainjectedsource-get-objectfilename.md)|ソースがコンパイルされたオブジェクトファイルの名前を取得します。|
|[IDiaInjectedSource::get_virtualFilename](../../debugger/debug-interface-access/idiainjectedsource-get-virtualfilename.md)|ファイル以外のソースコードに指定された名前を取得します。つまり、挿入されたコードです。|
|[IDiaInjectedSource::get_sourceCompression](../../debugger/debug-interface-access/idiainjectedsource-get-sourcecompression.md)|使用されるソース圧縮のインジケーターを取得します。|
|[IDiaInjectedSource::get_source](../../debugger/debug-interface-access/idiainjectedsource-get-source.md)|ソースコードのバイトを取得します。|

## <a name="remarks"></a>Remarks
挿入されたソースは、コンパイル時に挿入されるテキストです。 これは、で `#include` プリプロセッサを使用C++しているわけではありません。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
このインターフェイスを取得するには、 [IDiaEnumInjectedSources:: Item](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md)または[IDiaEnumInjectedSources:: Next](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md)メソッドを呼び出します。 @No__t_1 インターフェイスを取得する例については、 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)インターフェイスを参照してください。

## <a name="example"></a>例
この例では、`IDiaInjectedSource` インターフェイスから使用可能なデータを表示します。 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)インターフェイスを使用した別の方法については、 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)インターフェイスの例を参照してください。

```C++
void PrintInjectedSource(IDiaInjectedSource* pSource)
{
    ULONGLONG codeLength      = 0;
    DWORD     crc             = 0;
    DWORD     compressionType = 0;
    BSTR      sourceFilename  = NULL;
    BSTR      objectFilename  = NULL;
    BSTR      virtualFilename = NULL;

    std::cout << "Injected Source:" << std::endl;
    if (pSource != NULL)
    {
        if (pSource->get_crc(&crc) == S_OK &&
            pSource->get_sourceCompression(&compressionType) == S_OK &&
            pSource->get_length(&codeLength) == S_OK)
        {
            wprintf(L"  crc = %lu\n", crc);
            wprintf(L"  code length = %I64u\n",codeLength);
            wprintf(L"  compression type code = %lu\n", compressionType);
        }

        wprintf(L"  source filename: ");
        if (pSource->get_filename(&sourceFilename) == S_OK)
        {
            wprintf(L"%s", sourceFilename);
        }
        else
        {
            wprintf(L"<none>");
        }
        wprintf(L"\n");

        wprintf(L"  object filename: ");
        if (pSource->get_filename(&objectFilename) == S_OK)
        {
            wprintf(L"%s", objectFilename);
        }
        else
        {
            wprintf(L"<none>");
        }
        wprintf(L"\n");

        wprintf(L"  virtual filename: ");
        if (pSource->get_filename(&virtualFilename) == S_OK)
        {
            wprintf(L"%s", virtualFilename);
        }
        else
        {
            wprintf(L"<none>");
        }
        wprintf(L"\n");

        SysFreeString(sourceFilename);
        SysFreeString(objectFilename);
        SysFreeString(virtualFilename);
    }
}
```

## <a name="requirements"></a>［要件］
ヘッダー: Dia2

ライブラリ: diaguids

DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaEnumInjectedSources::Item](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md)
- [IDiaEnumInjectedSources::Next](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md)
- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)

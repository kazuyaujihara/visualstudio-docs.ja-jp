---
title: IDiaImageData |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData interface
ms.assetid: b696f350-fc08-4352-9287-a15e87512c1e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 75a81ae23db90b06915e7090a9f2918be3ff18ae
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743403"
---
# <a name="idiaimagedata"></a>IDiaImageData
モジュールまたはイメージのベースの位置とメモリオフセットの詳細を公開します。

## <a name="syntax"></a>構文

```
IDiaImageData : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、`IDiaImageData` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaImageData::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiaimagedata-get-relativevirtualaddress.md)|アプリケーションを基準として、モジュールの仮想メモリ内の場所を取得します。|
|[IDiaImageData::get_virtualAddress](../../debugger/debug-interface-access/idiaimagedata-get-virtualaddress.md)|イメージの仮想メモリ内の場所を取得します。|
|[IDiaImageData::get_imageBase](../../debugger/debug-interface-access/idiaimagedata-get-imagebase.md)|イメージの基になるメモリ位置を取得します。|

## <a name="remarks"></a>Remarks
一部のデバッグストリーム (.XDATA、PDATA) には、イメージにも格納されているデータのコピーが含まれています。 これらのストリームデータオブジェクトは、`IDiaImageData` インターフェイスに対してクエリを実行できます。 詳細については、このトピックの「呼び出し元のメモ」セクションを参照してください。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
このインターフェイスを取得するには、 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)オブジェクトで `QueryInterface` を呼び出します。 すべてのデバッグストリームで `IDiaImageData` インターフェイスがサポートされているわけではないことに注意してください。 たとえば、現在、`IDiaImageData` インターフェイスをサポートしているのは、.XDATA と PDATA のストリームだけです。

## <a name="example"></a>例
この例では、`IDiaImageData` インターフェイスをサポートするすべてのストリームについて、すべてのデバッグストリームを検索します。 そのようなストリームが見つかると、そのストリームに関する情報が表示されます。

```C++
void ShowImageData(IDiaSession *pSession)
{
    if (pSession != NULL)
    {
        CComPtr<IDiaEnumDebugStreams> pStreamsList;
        HRESULT hr;

        hr = pSession->getEnumDebugStreams(&pStreamsList);
        if (SUCCEEDED(hr))
        {
            LONG numStreams = 0;
            hr = pStreamsList->get_Count(&numStreams);
            if (SUCCEEDED(hr))
            {
                ULONG fetched = 0;
                for (LONG i = 0; i < numStreams; i++)
                {
                    CComPtr<IDiaEnumDebugStreamData> pStream;
                    hr = pStreamsList->Next(1,&pStream,&fetched);
                    if (fetched == 1)
                    {
                        CComPtr<IDiaImageData> pImageData;
                        hr = pStream->QueryInterface(__uuidof(IDiaImageData),
                                                     (void **)&pImageData);
                        if (SUCCEEDED(hr))
                        {
                            CComBSTR name;
                            hr = pStream->get_name(&name);
                            if (SUCCEEDED(hr))
                            {
                                wprintf(L"Stream %s:\n",(BSTR)name);
                            }
                            else
                            {
                                wprintf(L"Failed to get name of stream\n");
                            }

                            ULONGLONG imageBase = 0;
                            if (pImageData->get_imageBase(&imageBase) == S_OK)
                            {
                                wprintf(L"  image base = 0x%0I64x\n",imageBase);
                            }

                            DWORD relVA = 0;
                            if (pImageData->get_relativeVirtualAddress(&relVA) == S_OK)
                            {
                                wprintf(L"  relative virtual address = 0x%08lx\n",relVA);
                            }

                            ULONGLONG va = 0;
                            if (pImageData->get_virtualAddress(&va) == S_OK)
                            {
                                wprintf(L"  virtual address = 0x%0I64x\n", va);
                            }
                        }
                    }
                }
            }
        }
    }
}
```

## <a name="requirements"></a>［要件］
ヘッダー: Dia2

ライブラリ: diaguids

DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)

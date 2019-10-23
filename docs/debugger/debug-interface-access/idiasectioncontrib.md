---
title: IDiaSectionContrib |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib interface
ms.assetid: 371d40f6-ca0e-4d7e-9210-64d3768996c6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 807b9ada9b9424481a184e548e741131d66ab853
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742470"
---
# <a name="idiasectioncontrib"></a>IDiaSectionContrib
セクションの貢献度、つまりコンパイル単位によってイメージに対して提供される連続するメモリブロックを記述するデータを取得します。

## <a name="syntax"></a>構文

```
IDiaSectionContrib : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、`IDiaSectionContrib` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaSectionContrib::get_compiland](../../debugger/debug-interface-access/idiasectioncontrib-get-compiland.md)|このセクションを提供したコンパイル単位シンボルへの参照を取得します。|
|[IDiaSectionContrib::get_addressSection](../../debugger/debug-interface-access/idiasectioncontrib-get-addresssection.md)|貢献の住所のセクション部分を取得します。|
|[IDiaSectionContrib::get_addressOffset](../../debugger/debug-interface-access/idiasectioncontrib-get-addressoffset.md)|貢献の住所のオフセット部分を取得します。|
|[IDiaSectionContrib::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasectioncontrib-get-relativevirtualaddress.md)|貢献度のイメージ相対仮想アドレス (RVA) を取得します。|
|[IDiaSectionContrib::get_virtualAddress](../../debugger/debug-interface-access/idiasectioncontrib-get-virtualaddress.md)|貢献度の仮想アドレス (VA) を取得します。|
|[IDiaSectionContrib::get_length](../../debugger/debug-interface-access/idiasectioncontrib-get-length.md)|セクション内のバイト数を取得します。|
|[IDiaSectionContrib::get_notPaged](../../debugger/debug-interface-access/idiasectioncontrib-get-notpaged.md)|セクションがメモリからページアウトできないかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_nopad](../../debugger/debug-interface-access/idiasectioncontrib-get-nopad.md)|セクションを次のメモリ境界に埋め込むことができないかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_code](../../debugger/debug-interface-access/idiasectioncontrib-get-code.md)|セクションに実行可能コードが含まれているかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_code16bit](../../debugger/debug-interface-access/idiasectioncontrib-get-code16bit.md)|セクションに16ビットコードが含まれているかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_initializedData](../../debugger/debug-interface-access/idiasectioncontrib-get-initializeddata.md)|セクションに初期化されたデータが含まれているかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_uninitializedData](../../debugger/debug-interface-access/idiasectioncontrib-get-uninitializeddata.md)|セクションに初期化されていないデータが含まれているかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_informational](../../debugger/debug-interface-access/idiasectioncontrib-get-informational.md)|セクションにコメントまたは類似した情報が含まれているかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_remove](../../debugger/debug-interface-access/idiasectioncontrib-get-remove.md)|メモリ内のイメージの一部にする前に、セクションが削除されたかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_comdat](../../debugger/debug-interface-access/idiasectioncontrib-get-comdat.md)|セクションが COMDAT レコードであるかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_discardable](../../debugger/debug-interface-access/idiasectioncontrib-get-discardable.md)|セクションを破棄できるかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_notCached](../../debugger/debug-interface-access/idiasectioncontrib-get-notcached.md)|セクションをキャッシュできないかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_share](../../debugger/debug-interface-access/idiasectioncontrib-get-share.md)|セクションをメモリ内で共有できるかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_execute](../../debugger/debug-interface-access/idiasectioncontrib-get-execute.md)|セクションがコードとして実行可能かどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_read](../../debugger/debug-interface-access/idiasectioncontrib-get-read.md)|セクションを読み取ることができるかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_write](../../debugger/debug-interface-access/idiasectioncontrib-get-write.md)|セクションを書き込むことができるかどうかを示すフラグを取得します。|
|[IDiaSectionContrib::get_dataCrc](../../debugger/debug-interface-access/idiasectioncontrib-get-datacrc.md)|セクション内のデータの巡回冗長検査 (CRC) を取得します。|
|[IDiaSectionContrib::get_relocationsCrc](../../debugger/debug-interface-access/idiasectioncontrib-get-relocationscrc.md)|セクションの再配置情報の CRC を取得します。|
|[IDiaLineNumber::get_compilandId](../../debugger/debug-interface-access/idialinenumber-get-compilandid.md)|セクションのコンパイル単位識別子を取得します。|

## <a name="remarks"></a>Remarks

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
このインターフェイスは、 [IDiaEnumSectionContribs:: Item](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md)および[IDiaEnumSectionContribs:: Next](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md)メソッドを呼び出すことによって取得されます。 @No__t_1 インターフェイスを取得する例については、 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)インターフェイスを参照してください。

## <a name="example"></a>例
この関数は、各セクションのアドレスと、関連付けられているすべてのシンボルを表示します。 @No__t_1 インターフェイスの取得方法を確認するには、 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)インターフェイスを参照してください。

```C++
void PrintSectionContrib(IDiaSectionContrib* pSecContrib, IDiaSession* pSession)
{
    if (pSecContrib != NULL && pSession != NULL)
    {
        DWORD rva;
        if ( pSecContrib->get_relativeVirtualAddress( &rva ) == S_OK )
        {
            printf( "\taddr: 0x%.8X", rva );
            pSecContrib = NULL;
            CComPtr<IDiaSymbol> pSym;
            if ( psession->findSymbolByRVA( rva, SymTagNull, &pSym ) == S_OK )
            {
                CDiaBSTR name;
                DWORD    tag;
                pSym->get_symTag( &tag );
                pSym->get_name( &name );
                printf( "     symbol: %ws (%ws)\n",
                        name != NULL ? name : L"",
                        szTags[ tag ] );
            }
            else
            {
                printf( "<no symbol found?>\n" );
            }
        }
        else
        {
            DWORD isect;
            DWORD offset;
            pSecContrib->get_addressSection( &isect );
            pSecContrib->get_addressOffset( &offset );
            printf( "\taddr: 0x%.4X:0x%.8X", isect, offset );
            pSecContrib = NULL;
            CComPtr<IDiaSymbol> pSym;
            if ( SUCCEEDED( psession->findSymbolByAddr(
                                              isect,
                                              offset,
                                              SymTagNull,
                                              &pSym )
                          )
               )
            {
                CDiaBSTR name;
                DWORD    tag;
                pSym->get_symTag( &tag );
                pSym->get_name( &name );
                printf( "     symbol: %ws (%ws)\n",
                    name != NULL ? name : L"",
                    szTags[ tag ] );
            }
            else
            {
                printf( "<no symbol found?>\n" );
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
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)
- [IDiaEnumSectionContribs::Item](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md)
- [IDiaEnumSectionContribs::Next](../../debugger/debug-interface-access/idiaenumsectioncontribs-next.md)

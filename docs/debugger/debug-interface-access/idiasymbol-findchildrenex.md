---
title: 'IDiaSymbol:: findChildrenEx |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenEx
ms.assetid: 6e045045-da8c-4338-9423-81a1ca20c405
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 26fdced012baada390cdd0a112856b592d3c923e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741266"
---
# <a name="idiasymbolfindchildrenex"></a>IDiaSymbol::findChildrenEx
記号の子を取得します。 プログラムがの最適化を有効にしてコンパイルされている場合、返されるローカルシンボルには、ライブ範囲情報が含まれます。

## <a name="syntax"></a>構文

```C++
HRESULT findChildrenEx ( 
   enum SymTagEnum   symtag,
   LPCOLESTR         name,
   DWORD             compareFlags,
   IDiaEnumSymbols** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `symtag`

から[Symtagenum 列挙体](../../debugger/debug-interface-access/symtagenum.md)で定義されている、取得する子のシンボルタグを指定します。 すべての子を取得するには、を `SymTagNull` に設定します。

 `name`

から取得する子の名前を指定します。 すべての子を取得するには、を `NULL` に設定します。

 `compareFlags`

から名前の一致に適用する比較オプションを指定します。 [Namesearchoptions 列挙](../../debugger/debug-interface-access/namesearchoptions.md)列挙の値は、単独で、または組み合わせて使用できます。

 `ppResult`

入出力取得した子シンボルのリストを格納している[IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 シンボルの少なくとも1つの子が見つかった場合は `S_OK` を返し、子が見つからなかった場合は `S_FALSE` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、 [IDiaSymbol:: findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)の拡張バージョンです。

## <a name="requirements"></a>［要件］
 ヘッダー: Dia2

 ライブラリ: diaguids

 DLL: msdia100

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
- [NameSearchOptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)
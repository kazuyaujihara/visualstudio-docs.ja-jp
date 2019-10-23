---
title: 'IDiaSymbol:: findChildren |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildren method
ms.assetid: 5fe7573a-e48b-428d-9c17-7421b7209246
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f3c62271f6324e50a68de393cfa668c69ba4a935
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741301"
---
# <a name="idiasymbolfindchildren"></a>IDiaSymbol::findChildren
記号の子を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findChildren ( 
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

から名前の一致に適用される比較オプションを指定します。 [Namesearchoptions 列挙](../../debugger/debug-interface-access/namesearchoptions.md)列挙の値は、単独で、または組み合わせて使用できます。

 `ppResult`

入出力取得した子シンボルのリストを格納している[IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 シンボルの少なくとも1つの子が見つかった場合は `S_OK` を返し、子が見つからなかった場合は `S_FALSE` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、このシンボルを最初のパラメーターとして[IDiaSession:: findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)メソッドを呼び出すことと同じです。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
- [NameSearchOptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)
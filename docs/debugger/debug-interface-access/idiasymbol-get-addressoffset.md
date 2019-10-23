---
title: 'IDiaSymbol:: get_addressOffset |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_addressOffset method
ms.assetid: c15639b0-7f37-46c7-891b-40273b7f6319
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9290173fc9dcfdc07c7c0afbb33c741fe3e53f6c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741084"
---
# <a name="idiasymbolget_addressoffset"></a>IDiaSymbol::get_addressOffset
アドレスの場所のオフセット部分を取得します。 [LocationType 列挙](../../debugger/debug-interface-access/locationtype.md)が `LocIsStatic` に設定されている場合は、を使用します。

## <a name="syntax"></a>構文

```C++
HRESULT get_addressOffset ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力アドレスの場所のオフセット部分を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

> [!NOTE]
> @No__t_0 の戻り値は、そのシンボルに対してプロパティを使用できないことを意味します。

## <a name="remarks"></a>Remarks
 外部 DLL に配置されている静的メンバーの場合、このメソッドは、このメソッドによって返されるオフセットを0にすることができます。このメソッドは、メンバーの仮想アドレスの取得に依存します。 仮想アドレスは、 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)インターフェイスの[IDiaSession::p ut_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)メソッドが、DLL の読み込みアドレスを指定する0以外のパラメーターを使用して呼び出されている場合にのみ有効です。

 アドレスのセクション部分を取得するには、 [IDiaSymbol:: get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)メソッドを呼び出します。

## <a name="requirements"></a>［要件］

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2|
|バージョン:|DIA SDK v1.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)
- [IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)
- [IDiaSession::put_loadAddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
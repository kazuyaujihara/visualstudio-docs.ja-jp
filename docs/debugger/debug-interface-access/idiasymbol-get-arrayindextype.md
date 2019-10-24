---
title: 'IDiaSymbol:: get_arrayIndexType |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_arrayIndexType method
ms.assetid: cd63b9ec-9694-406c-b37f-bde6bd5fcbf2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 94a1ff47ce7ad6436f74f648edd27e02f98e54a6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741050"
---
# <a name="idiasymbolget_arrayindextype"></a>IDiaSymbol::get_arrayIndexType
シンボルの配列インデックスの種類のシンボルインターフェイスを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_arrayIndexType ( 
   IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力シンボルの配列インデックスの種類を表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

> [!NOTE]
> @No__t_0 の戻り値は、そのシンボルに対してプロパティを使用できないことを意味します。

## <a name="remarks"></a>Remarks
 一部の言語では、配列のインデックスとして使用される型を指定できます。 このメソッドから返されるシンボルは、その型を指定します。

## <a name="requirements"></a>［要件］

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2|
|バージョン:|DIA SDK v1.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
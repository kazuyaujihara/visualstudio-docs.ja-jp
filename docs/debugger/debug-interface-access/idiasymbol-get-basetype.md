---
title: 'IDiaSymbol:: get_baseType |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_baseType method
ms.assetid: 5c69a241-a8d3-48ed-8b36-27463a196572
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0a3d1bb8b2f3095fd35488c47f823e7b3603995b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740917"
---
# <a name="idiasymbolget_basetype"></a>IDiaSymbol::get_baseType
このシンボルの基本型を取得し<em>ます。</em>

## <a name="syntax"></a>構文

```C++
HRESULT get_baseType (
    DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
`pRetVal`

入出力シンボルの基本型を指定する[Basictype 列挙](../../debugger/debug-interface-access/basictype.md)型の値を返します。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

> [!NOTE]
> @No__t_0 の戻り値は、そのシンボルに対してプロパティを使用できないことを意味します。

## <a name="remarks"></a>Remarks
シンボルの基本型を決定するには、最初にシンボルの型を取得し、次に基本型に対して返された型を問い合わせるします。 一部のシンボルには、構造体の名前など、基本型を使用できない場合があることに注意してください。

## <a name="example"></a>例

```C++
IDiaSymbol* pType;
CComPtr<IDiaSymbol> pBaseType;
if (pType->get_type( &pBaseType ) == S_OK)
{
    BasicType btBaseType;
    if (pBaseType->get_baseType((DWORD *)&btBaseType) == S_OK)
    {
        // Do something with basic type.
    }
}
```

## <a name="requirements"></a>［要件］

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2|
|バージョン:|DIA SDK v1.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [BasicType 列挙型](../../debugger/debug-interface-access/basictype.md)
- [IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)

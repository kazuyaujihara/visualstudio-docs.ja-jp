---
title: 'IDiaSymbol:: get_classParent |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_classParent method
ms.assetid: 99db875a-caae-4d60-ae70-64bc8a9f6fba
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 36dfed97fb8abd30f97c4068da94148715cae5c7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740856"
---
# <a name="idiasymbolget_classparent"></a>IDiaSymbol::get_classParent
シンボルの親クラスへの参照を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_classParent ( 
   IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力シンボルの親クラスを表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

> [!NOTE]
> @No__t_0 の戻り値は、そのシンボルに対してプロパティを使用できないことを意味します。

## <a name="requirements"></a>［要件］

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2|
|バージョン:|DIA SDK v1.0|

## <a name="remarks"></a>Remarks
 クラスの親にできるシンボルの種類は、「[シンボル型のクラス階層](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)」に記載されています。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [シンボル型のクラス階層](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)
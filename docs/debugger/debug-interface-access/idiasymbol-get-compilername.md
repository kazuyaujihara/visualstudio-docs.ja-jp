---
title: 'IDiaSymbol:: get_compilerName |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_compilerName method
ms.assetid: 66eaaf72-68d4-40ee-b132-97bea9fe395c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3fd64d2f1a18df2d41a7d39f4ce474d601e194c7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740812"
---
# <a name="idiasymbolget_compilername"></a>IDiaSymbol::get_compilerName
[コンパイル単位](../../debugger/debug-interface-access/compiland.md)の生成に使用されるコンパイラの名前を返します。

## <a name="syntax"></a>構文

```C++
HRESULT get_compilerName (
   BSTR *pName
);
```

#### <a name="parameters"></a>パラメーター
 コンパイラの Unicode 名を格納する BSTR へのポインター `pName` ます。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

> [!NOTE]
> @No__t_0 の戻り値は、そのシンボルに対してプロパティを使用できないことを意味します。

## <a name="remarks"></a>Remarks

## <a name="requirements"></a>［要件］

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2|
|バージョン:|DIA SDK v1.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
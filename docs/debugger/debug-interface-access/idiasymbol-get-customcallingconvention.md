---
title: 'IDiaSymbol:: get_customCallingConvention |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_customCallingConvention method
ms.assetid: 0aa97951-f7e1-4fa5-a87f-2920460c122d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 01fb33108c9952b8543d36b64b7743f4c0531be5
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740732"
---
# <a name="idiasymbolget_customcallingconvention"></a>IDiaSymbol::get_customCallingConvention
関数にカスタム呼び出し規約があるかどうかを指定するフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_customCallingConvention(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>パラメーター
 `pFlag`

入出力関数にカスタム呼び出し規約がある場合は `TRUE` を返します。それ以外の場合、`FALSE`を返します。関数には既知の呼び出し規約があります。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK`を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

> [!NOTE]
> `S_FALSE` の戻り値は、そのシンボルに対してプロパティを使用できないことを意味します。

## <a name="requirements"></a>［要件］

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2|
|バージョン:|DIA SDK v1.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
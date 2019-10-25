---
title: 'IDiaSymbol:: get_callingConvention |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_callingConvention method
ms.assetid: 355d3877-b6b6-45fd-a1d8-baed428d8f96
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b1b0581e7a49ac8c8681077a7f40133498a48789
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740877"
---
# <a name="idiasymbolget_callingconvention"></a>IDiaSymbol::get_callingConvention
メソッドの呼び出し規約のインジケーターを返します。

## <a name="syntax"></a>構文

```C++
HRESULT get_callingConvention ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力メソッドの呼び出し規約を指定する[CV_call_e enumeration](../../debugger/debug-interface-access/cv-call-e.md)列挙体から値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

> [!NOTE]
> @No__t_0 の戻り値は、そのシンボルに対してプロパティを使用できないことを意味します。

## <a name="requirements"></a>［要件］

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2|
|バージョン:|DIA SDK v1.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [CV_call_e 列挙型](../../debugger/debug-interface-access/cv-call-e.md)
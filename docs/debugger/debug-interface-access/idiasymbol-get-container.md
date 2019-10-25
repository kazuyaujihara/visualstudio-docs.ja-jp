---
title: 'IDiaSymbol:: get_container |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_container method
ms.assetid: 24e832eb-80b3-484c-a41b-11477ec9de99
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0533eb2cdea1dd3e1bea3d64e2b94ce29a09353d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740772"
---
# <a name="idiasymbolget_container"></a>IDiaSymbol::get_container
この関数は、このシンボルの親/コンテナーを表すシンボルへのポインターを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_container(
   IDiaSymbol **pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力このシンボルのコンテナーに関する情報を格納している `IDiaSymbol` へのポインターを返します。

## <a name="return-value"></a>戻り値
 成功した場合、は S_OK を返します。それ以外の場合は、S_FALSE またはエラーコードを返します。

> [!NOTE]
> S_FALSE の戻り値は、そのシンボルに対してプロパティを使用できないことを意味します。

## <a name="requirements"></a>［要件］

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|dia2|
|バージョン:|DIA SDK v1.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
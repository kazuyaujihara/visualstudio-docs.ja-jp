---
title: Idiasymbol::get_hasseh |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hasSEH method
ms.assetid: 1a709ded-22c8-464c-97be-eba5e464210c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41987007dd5121dff8cce1eb91ea9e1c4d93578c
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64816350"
---
# <a name="idiasymbolgethasseh"></a>IDiaSymbol::get_hasSEH
関数がいずれかを含めるかどうかを指定するフラグを取得します。[構造化例外処理 (C/C++)](/cpp/cpp/structured-exception-handling-c-cpp) (例: _ _try/\__except ブロック)。

## <a name="syntax"></a>構文

```C++
HRESULT get_hasSEH(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>パラメーター
 `pFlag`

[out]返します`TRUE`メンバー関数に構造化例外処理ブロックがある場合は、関数を返しますそれ以外の場合、`FALSE`します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="requirements"></a>必要条件

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|Dia2.h|
|バージョン:|DIA SDK バージョン 8.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [構造化例外処理 (C/C++)](/cpp/cpp/structured-exception-handling-c-cpp)

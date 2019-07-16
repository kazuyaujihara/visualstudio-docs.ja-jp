---
title: Idiasymbol::get_access |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_access method
ms.assetid: 908976ae-95c4-4020-89c9-de137f727f98
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fcf510cd9c74e22e0d028552b26c85b1f3d59bd4
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64813907"
---
# <a name="idiasymbolgetaccess"></a>IDiaSymbol::get_access
クラス メンバーのアクセス修飾子を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_access ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]値を返します、 [CV_access_e 列挙型](../../debugger/debug-interface-access/cv-access-e.md)クラスのメンバーのアクセス修飾子を指定する列挙体。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティがシンボルを使用できないことを意味します。

## <a name="requirements"></a>必要条件

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|Dia2.h|
|バージョン:|DIA SDK v7.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [CV_access_e 列挙型](../../debugger/debug-interface-access/cv-access-e.md)
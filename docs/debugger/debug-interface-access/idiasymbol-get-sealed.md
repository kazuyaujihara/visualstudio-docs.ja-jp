---
title: Idiasymbol::get_sealed |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_sealed method
ms.assetid: cd1fef1f-47de-47c7-885f-f6f0a9a07d8c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4c75148fdf8453590be7eb0f9fbde95e4bb4b981
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64791688"
---
# <a name="idiasymbolgetsealed"></a>IDiaSymbol::get_sealed
クラスまたはメソッドがシールされているかどうかを指定するフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_sealed( 
   BOOL* pRetVal)
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します`TRUE`クラスまたはメソッドがシールされている場合を返しますそれ以外の場合、`FALSE`します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="remarks"></a>Remarks
 シール クラスは、基底クラスとして使用できません。 シール メソッドは、上書きをすることはできません。

## <a name="requirements"></a>必要条件
 ヘッダー:Dia2.h

 ライブラリ: diaguids.lib

 DLL: msdia100.dll

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
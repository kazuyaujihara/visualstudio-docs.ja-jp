---
title: Idiasymbol::get_thisadjust |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_thisAdjust method
ms.assetid: 56b9a147-e8c0-4d4b-a42a-398214dd5f86
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2dfdfb07f0ea20cf13a56eed7f380e3ec195fe52
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64800784"
---
# <a name="idiasymbolgetthisadjust"></a>IDiaSymbol::get_thisAdjust
論理取得`this`調整メソッドの権限を保持します。

## <a name="syntax"></a>構文

```C++
HRESULT get_thisAdjust ( 
   LONG* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します、論理`this`調整メソッドの権限を保持します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="remarks"></a>Remarks
 複数の継承によってメソッド自体が、真を計算する必要があります`this`値のオフセット位置に追加することによって`this`します。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
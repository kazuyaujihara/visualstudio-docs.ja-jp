---
title: IDiaSymbol::get_stride |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4264742a-3d91-44b9-9d14-87adbc77f0f0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c581668668a208a9bcf35a1b39d1b3d384a4f8a3
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "62841615"
---
# <a name="idiasymbolgetstride"></a>IDiaSymbol::get_stride
マトリックスまたは strided 配列のストライドを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_stride(
   DWORD* pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]ポインター、 `DWORD` stride を保持しています。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)

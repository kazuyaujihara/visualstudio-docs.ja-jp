---
title: IDiaSymbol::get_unmodifiedTypeId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4f7fc73c-f524-4d7a-b378-a9ab99a96104
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 99d549a0edc56d48d686424c35f22fc7ea74438b
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "62841187"
---
# <a name="idiasymbolgetunmodifiedtypeid"></a>IDiaSymbol::get_unmodifiedTypeId
元の (変更なし) の型の ID を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_unmodifiedTypeId(
   DWORD* pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]ポインター、 `DWORD` ID を保持します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)

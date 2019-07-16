---
title: IDiaSymbol::get_subType |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0b3cbf77-8f11-434a-ad60-ea9829fec6fa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4639df568b033eea03ff4ad61c4ddd4e512e2bfc
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "62835465"
---
# <a name="idiasymbolgetsubtype"></a>IDiaSymbol::get_subType
サブ タイプを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_subType(
   IDiaSymbol** pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]サブ タイプへのポインター。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)

---
title: IDiaSymbol::get_isPointerToMemberFunction |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aa9b5599-9602-41be-ab50-d84b90bee72f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b666aa19e574702655178790b8aa0463a0d5c2d5
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56625674"
---
# <a name="idiasymbolgetispointertomemberfunction"></a>IDiaSymbol::get_isPointerToMemberFunction
このシンボルがメンバー関数へのポインターであるかどうかを指定します。

## <a name="syntax"></a>構文

```C++
HRESULT get_isPointerToMemberFunction(
   BOOL* pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]ポインターを`BOOL`シンボルは、メンバー関数へのポインターであるかどうかを指定します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)

---
title: Idiasession::symsareequiv |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0253104cf29e86825fadc8c8bd18133e0d3cf593
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839076"
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
2 つのシンボルが等しいかどうかを確認します。

## <a name="syntax"></a>構文

```C++
HRESULT symsAreEquiv ( 
   IDiaSymbol* symbolA,
   IDiaSymbol* symbolB
);
```

#### <a name="parameters"></a>パラメーター
 `symbolA`

[in]最初の[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)比較に使用されるオブジェクト。

 `symbolB`

[in]2 番目の`IDiaSymbol`比較に使用されるオブジェクト。

## <a name="return-value"></a>戻り値
 シンボルと同じ場合を返します`S_OK`。 それ以外を返します`S_FALSE`、シンボルが同じではありません。 それ以外の場合、エラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
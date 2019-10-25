---
title: 'IDiaSession:: symsAreEquiv |Microsoft Docs'
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
ms.openlocfilehash: 61cfc582f11670af8c956c3334681284ce5172a6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741862"
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
2つの記号が等しいかどうかを確認します。

## <a name="syntax"></a>構文

```C++
HRESULT symsAreEquiv ( 
   IDiaSymbol* symbolA,
   IDiaSymbol* symbolB
);
```

#### <a name="parameters"></a>パラメーター
 `symbolA`

から比較で使用される最初の[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクト。

 `symbolB`

から比較で使用される2番目の `IDiaSymbol` オブジェクト。

## <a name="return-value"></a>戻り値
 シンボルが等しい場合は、`S_OK` を返します。それ以外の場合、`S_FALSE` を返します。シンボルは等価ではありません。 それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
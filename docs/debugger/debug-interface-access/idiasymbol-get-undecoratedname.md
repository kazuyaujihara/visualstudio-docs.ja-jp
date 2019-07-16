---
title: Idiasymbol::get_undecoratedname |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_undecoratedName method
ms.assetid: e49edf25-a51d-4787-bd5b-2bf5af827c8c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d9650c2ea67d847f225f047d62dd7d1867a61d4d
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64809175"
---
# <a name="idiasymbolgetundecoratedname"></a>IDiaSymbol::get_undecoratedName
C++ の装飾、またはリンケージ、名前の非装飾名を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_undecoratedName ( 
   BSTR* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]非装飾名を返します、C++装飾名。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
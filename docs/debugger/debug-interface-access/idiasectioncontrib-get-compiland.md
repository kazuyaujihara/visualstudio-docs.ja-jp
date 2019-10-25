---
title: 'IDiaSectionContrib:: get_compiland |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_compiland method
ms.assetid: c0496f6f-f8f2-435f-8674-6c32db6c5934
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d9a398d7cc0ff8efc9dacc726205cd0d8fa02473
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742718"
---
# <a name="idiasectioncontribget_compiland"></a>IDiaSectionContrib::get_compiland
このセクションを提供したコンパイル単位シンボルへの参照を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_compiland ( 
   IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力このセクションを提供したコンパイル単位を表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
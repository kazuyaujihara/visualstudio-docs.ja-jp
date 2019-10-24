---
title: 'IDiaEnumSymbols:: Skip |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbols::Skip method
ms.assetid: e601fbc9-b10b-41c7-8180-959e57efabe8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9252826470decd3cddfabdcc2a00e22037d5de5c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743906"
---
# <a name="idiaenumsymbolsskip"></a>IDiaEnumSymbols::Skip
列挙シーケンス内の指定された数のシンボルをスキップします。

## <a name="syntax"></a>構文

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>パラメーター
 celt

からスキップする列挙シーケンス内のシンボルの数。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、スキップするシンボルがなくなった場合は `S_FALSE` を返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
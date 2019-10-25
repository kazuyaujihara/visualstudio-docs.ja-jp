---
title: 'IDiaEnumSourceFiles:: Skip |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Skip method
ms.assetid: 4821e6dd-d33f-403d-857d-e3ae81e4a9e3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d7aef3ea724bbb50f0342032a62e0044a1f0eb30
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744052"
---
# <a name="idiaenumsourcefilesskip"></a>IDiaEnumSourceFiles::Skip
列挙シーケンス内の指定された数のソースファイルをスキップします。

## <a name="syntax"></a>構文

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>パラメーター
 celt

からスキップする列挙シーケンス内のソースファイルの数。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、スキップするソースファイルがない場合は `S_FALSE` を返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)
---
title: 'IDiaEnumDebugStreamData:: Skip |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreamData::Skip method
ms.assetid: 106ae1d3-a379-4077-babf-2665e697b0c4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f2f331d7a91e9dbc6dbf0dea2e8a5b91f08de584
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744828"
---
# <a name="idiaenumdebugstreamdataskip"></a>IDiaEnumDebugStreamData::Skip
列挙されたシーケンス内の指定した数のレコードをスキップします。

## <a name="syntax"></a>構文

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>パラメーター
 celt

から列挙されたシーケンスでスキップするレコードの数。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、スキップするレコードがなくなった場合は `S_FALSE` を返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
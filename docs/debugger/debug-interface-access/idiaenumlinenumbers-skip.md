---
title: Idiaenumlinenumbers::skip |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Skip method
ms.assetid: d182c269-8c76-4d8b-8275-c6807c5ae4e1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e68eccfebfc5218d59649aa09162b20467ceb670
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56616548"
---
# <a name="idiaenumlinenumbersskip"></a>IDiaEnumLineNumbers::Skip
指定された数の列挙体シーケンス内の行番号をスキップします。

## <a name="syntax"></a>構文

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>パラメーター
 celt

[in]スキップする列挙体シーケンス内の行番号の数。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`をスキップする複数の行番号なしがある場合。

## <a name="see-also"></a>関連項目
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
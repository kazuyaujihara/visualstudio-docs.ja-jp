---
title: 'IDiaEnumFrameData:: Skip |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Skip method
ms.assetid: 67140b4c-7125-4895-932d-42412326da29
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c49aaf1f648a52e1701088b6579eda55cde6c355
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744568"
---
# <a name="idiaenumframedataskip"></a>IDiaEnumFrameData::Skip
列挙シーケンス内の指定された数のフレームデータ要素をスキップします。

## <a name="syntax"></a>構文

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>パラメーター
 celt

からスキップする列挙シーケンス内のフレームデータ要素の数。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、スキップするレコードがなくなった場合は `S_FALSE` を返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)
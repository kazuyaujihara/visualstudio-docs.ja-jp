---
title: Idiasectioncontrib::get_read |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_read method
ms.assetid: 68bfb35c-eabd-412a-bc8f-3094703b98c4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 864de61a3cc0c17dfa81770b3be35f6e5879541d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635762"
---
# <a name="idiasectioncontribgetread"></a>IDiaSectionContrib::get_read
セクションを読み取れるかどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_read ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します`TRUE`セクションを読み取ることができます。 場合を返しますそれ以外の場合、`FALSE`します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
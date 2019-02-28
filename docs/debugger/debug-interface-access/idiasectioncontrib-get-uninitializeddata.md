---
title: Idiasectioncontrib::get_uninitializeddata |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_uninitializedData method
ms.assetid: 39736f35-6c73-4f54-a092-517192e417ff
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 08baf81c327457ac250d91bcbb7d9951a0290459
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56637816"
---
# <a name="idiasectioncontribgetuninitializeddata"></a>IDiaSectionContrib::get_uninitializedData
セクションに初期化されていないデータが含まれているかどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_uninitializedData ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します`TRUE`セクションには、初期化されていないデータが含まれている場合を返しますそれ以外の場合、`FALSE`します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
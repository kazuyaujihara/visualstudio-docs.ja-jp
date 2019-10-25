---
title: 'IDiaSectionContrib:: get_initializedData |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_initializedData method
ms.assetid: f5c108be-a0cc-408b-9590-b8d44361810c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6386fc6bb460f7e0947680a9776af7646f1bec14
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742634"
---
# <a name="idiasectioncontribget_initializeddata"></a>IDiaSectionContrib::get_initializedData
セクションに初期化されたデータが含まれているかどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_initializedData ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力セクションに初期化されたデータが含まれている場合は `TRUE` を返します。それ以外の場合は `FALSE` を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
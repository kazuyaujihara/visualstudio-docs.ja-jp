---
title: 'IDiaSectionContrib:: get_share |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_share method
ms.assetid: 05c4c896-4419-4166-8bb2-8d0934dc14b5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2ecdb0bf3690f1f61da68fb1976945d196add02e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742518"
---
# <a name="idiasectioncontribget_share"></a>IDiaSectionContrib::get_share
セクションをメモリ内で共有できるかどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_share ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力セクションがメモリ内で共有可能な場合は `TRUE` を返します。それ以外の場合は `FALSE` を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
---
title: 'IDiaSectionContrib:: get_informational |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_informational method
ms.assetid: 5351e89f-7db1-4f8e-9e57-2dd1c74002e0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e425c8bc4e1e3973dac5becc39f3e6c6e9f8dfe8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742645"
---
# <a name="idiasectioncontribget_informational"></a>IDiaSectionContrib::get_informational
セクションにコメントまたは類似した情報が含まれているかどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_informational(
   BOOL* pRetVal
};
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力セクションにコメントまたはその他の情報が含まれている場合は `TRUE` を返します。それ以外の場合は `FALSE` を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 通常、ディレクティブセクションには情報が含まれています。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
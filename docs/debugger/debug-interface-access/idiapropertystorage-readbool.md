---
title: 'IDiaPropertyStorage:: ReadBOOL |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadBOOL
ms.assetid: ad1822db-4572-48f7-9919-f8137f6701f2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d776e37bab189e61d0264f4cbda24f89cb4501ce
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742939"
---
# <a name="idiapropertystoragereadbool"></a>IDiaPropertyStorage::ReadBOOL
プロパティセット内の `BOOL` 値を読み取ります。

## <a name="syntax"></a>構文

```C++
HRESULT ReadBOOL ( 
   PROPID id,
   BOOL*  pValue
);
```

#### <a name="parameters"></a>パラメーター
 `id`

から読み取るプロパティの識別子 (`PROPID` は、WTypes. h で `ULONG` として定義されています)。

 `pValue`

入出力プロパティ値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 プロパティが `BOOL` 型でない場合は `E_INVALIDARG` を返します。

## <a name="remarks"></a>Remarks
 一貫した結果を得るために、`BOOL` 値を解釈して0以外の値が `TRUE`、0が `FALSE` されるようにします。

## <a name="see-also"></a>関連項目
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
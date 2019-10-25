---
title: 'IDiaPropertyStorage:: ReadLONG |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadLONG
ms.assetid: 32054cbc-db55-4513-a1b4-de80e77aac8a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: af9d65c571c5e0a281b968d922c9b5170bd1c561
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742899"
---
# <a name="idiapropertystoragereadlong"></a>IDiaPropertyStorage::ReadLONG
プロパティセット内の `LONG` 値を読み取ります。

## <a name="syntax"></a>構文

```C++
HRESULT ReadDLONG ( 
   PROPID id,
   LONG*  pValue
);
```

#### <a name="parameters"></a>パラメーター
 `id`

から読み取るプロパティの識別子 (`PROPID` は、WTypes. h で `ULONG` として定義されています)。

 `pValue`

入出力プロパティ値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 プロパティが `LONG` 型でない場合は `E_INVALIDARG` を返します。

## <a name="remarks"></a>Remarks
 @No__t_0 は、Windows によって32ビット符号付き整数として定義されます。

## <a name="see-also"></a>関連項目
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
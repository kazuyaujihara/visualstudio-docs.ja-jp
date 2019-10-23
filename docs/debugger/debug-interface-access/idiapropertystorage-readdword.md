---
title: IDiaPropertyStorage::ReadDWORD | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadDWORD
ms.assetid: 5f4c034e-a9d3-4560-94b5-ede524741439
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1764ec83a69dcc5daff267767594473bf690b341
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742906"
---
# <a name="idiapropertystoragereaddword"></a>IDiaPropertyStorage::ReadDWORD
プロパティセット内の `DWORD` 値を読み取ります。

## <a name="syntax"></a>構文

```C++
HRESULT ReadDWORD ( 
   PROPID id,
   DWORD* pValue
);
```

#### <a name="parameters"></a>パラメーター
 `id`

から読み取るプロパティの識別子 (`PROPID` は、WTypes. h で `ULONG` として定義されています)。

 `pValue`

入出力プロパティ値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 プロパティが `DWORD` 型でない場合は `E_INVALIDARG` を返します。

## <a name="remarks"></a>Remarks
 @No__t_0 は、Windows によって32ビット符号なし整数として定義されます。

## <a name="see-also"></a>関連項目
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
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
ms.openlocfilehash: 5b4709a218f6586320e96f79ea8a9f423f537c7f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635931"
---
# <a name="idiapropertystoragereaddword"></a>IDiaPropertyStorage::ReadDWORD
読み取り`DWORD`プロパティ セット内の値。

## <a name="syntax"></a>構文

```C++
HRESULT ReadDWORD ( 
   PROPID id,
   DWORD* pValue
);
```

#### <a name="parameters"></a>パラメーター
 `id`

[in]読み取るプロパティの識別子 (`PROPID`として WTypes.h で定義されている、 `ULONG`)。

 `pValue`

[out]プロパティ値を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外の場合はエラー コードを返します。 返します`E_INVALIDARG`型のプロパティがない場合`DWORD`します。

## <a name="remarks"></a>解説
 A `DWORD` 32 ビット符号なし整数としての Windows によって定義されます。

## <a name="see-also"></a>関連項目
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
---
title: 'IDiaPropertyStorage:: ReadPropertyNames |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f554485ae56a9d5f190c749879545165d299531c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742868"
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
指定されたプロパティ識別子の対応する文字列名を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT ReadPropertyNames (
   ULONG         cpropid,
   PROPID const* rgpropid,
   BSTR*         rglpwstrName
);
```

#### <a name="parameters"></a>パラメーター
 `cpropid`

から@No__t_0 内のプロパティ id の数。

 `rgpropid`

から名前を取得する対象のプロパティ id の配列 (`PROPID` は、WTypes .h で `ULONG` として定義されています)。

 `rglpwstrName`

[入力、出力]指定されたプロパティ id のプロパティ名の配列。 配列は、要求された数のプロパティ名を保持するために事前に割り当てられている必要があり、少なくとも `cpropid``BSTR` の文字列を保持できる必要があります。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 返されたプロパティ名は、不要になったときに (`SysFreeString` 関数を呼び出すことによって) 解放する必要があります。

## <a name="see-also"></a>関連項目
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
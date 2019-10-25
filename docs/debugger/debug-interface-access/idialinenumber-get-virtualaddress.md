---
title: 'IDiaLineNumber:: get_virtualAddress |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_virtualAddress method
ms.assetid: 9048ef91-a59d-4ad8-90cb-4c13d0989241
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 103d83e3b305e13720b7673dae89f942eb2f692d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743116"
---
# <a name="idialinenumberget_virtualaddress"></a>IDiaLineNumber::get_virtualAddress
ブロックの仮想アドレス (VA) を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_virtualAddress ( 
   ULONGLONG* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力ブロックの仮想アドレスを返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
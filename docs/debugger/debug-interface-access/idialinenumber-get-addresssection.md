---
title: 'IDiaLineNumber:: get_addressSection |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_addressSection method
ms.assetid: a01c1bae-04b2-4c30-8621-60939a3124c2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2458ee3eb26bed46c8699c9fe41dadbde091bfad
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743268"
---
# <a name="idialinenumberget_addresssection"></a>IDiaLineNumber::get_addressSection
ブロックが開始されるメモリアドレスのセクション部分を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_addressSection ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 の場合は、

入出力ブロックが開始されるメモリアドレスのセクション部分を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="example"></a>例

```C++
CComPtr< IDiaLineNumber > pLine;
DWORD seg;
pLine->get_addressSection( &seg );
```

## <a name="see-also"></a>関連項目
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
- [IDiaLineNumber::get_addressOffset](../../debugger/debug-interface-access/idialinenumber-get-addressoffset.md)
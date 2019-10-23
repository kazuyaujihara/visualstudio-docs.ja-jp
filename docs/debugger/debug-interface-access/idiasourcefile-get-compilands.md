---
title: 'IDiaSourceFile:: get_compilands |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_compilands method
ms.assetid: 57deb50a-9c22-43ea-a80c-eab205997bc4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dea4b53daae31c90753ef7afb293e69157f58e41
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741810"
---
# <a name="idiasourcefileget_compilands"></a>IDiaSourceFile::get_compilands
このファイルを参照している行番号を持つ compilands の列挙子を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_compilands ( 
   IDiaEnumSymbols** ppRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `ppRetVal`

入出力このファイルを参照している行番号を持つすべての compilands の一覧を含む[IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
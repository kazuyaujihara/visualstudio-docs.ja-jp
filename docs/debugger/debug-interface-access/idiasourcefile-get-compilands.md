---
title: Idiasourcefile::get_compilands |Microsoft Docs
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
ms.openlocfilehash: 15ebc8296bdf78515b31d38a7543a4f41db84664
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838247"
---
# <a name="idiasourcefilegetcompilands"></a>IDiaSourceFile::get_compilands
このファイルを参照する行番号のコンパイル単位の列挙子を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_compilands ( 
   IDiaEnumSymbols** ppRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `ppRetVal`

[out]返します、 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)をこのファイルを参照する行番号を持つすべてのコンパイル単位の一覧を格納しているオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
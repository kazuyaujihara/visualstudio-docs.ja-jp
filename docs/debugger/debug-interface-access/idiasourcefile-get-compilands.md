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
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56613025"
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
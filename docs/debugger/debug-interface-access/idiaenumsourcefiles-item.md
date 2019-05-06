---
title: Idiaenumsourcefiles::item |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Item method
ms.assetid: 3c19d7ed-0232-4b0e-9b10-f33ed9e0c93b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 403aa09a487ea1587ab30389f180afecec5ac6bf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62833339"
---
# <a name="idiaenumsourcefilesitem"></a>IDiaEnumSourceFiles::Item
インデックスを使用してソース ファイルを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item ( 
   DWORD            index,
   IDiaSourceFile** sourceFile
);
```

#### <a name="parameters"></a>パラメーター
 インデックス

[in]インデックス、 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)を取得するオブジェクト。 インデックスは 0 ~ の範囲内で、 `count`-1 の場合、`count`によって返される、 [idiaenumsourcefiles::get_count](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md)メソッド。

 sourceFile

[out]返します、 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)目的のソース ファイルを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
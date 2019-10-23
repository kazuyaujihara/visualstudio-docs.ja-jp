---
title: 'IDiaEnumSourceFiles:: Item |Microsoft Docs'
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
ms.openlocfilehash: 352c9516180c0ee0021fca4e0913f154f3b8d46f
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744095"
---
# <a name="idiaenumsourcefilesitem"></a>IDiaEnumSourceFiles::Item
インデックスを使ってソースファイルを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item ( 
   DWORD            index,
   IDiaSourceFile** sourceFile
);
```

#### <a name="parameters"></a>パラメーター
 インデックス

から取得する[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)オブジェクトのインデックス。 インデックスは 0 ~ `count`-1 の範囲にあり、`count` は[IDiaEnumSourceFiles:: get_Count](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md)メソッドによって返されます。

 sourceFile

入出力目的のソースファイルを表す[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
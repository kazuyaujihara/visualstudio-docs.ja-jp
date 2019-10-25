---
title: 'IDiaSourceFile:: get_fileName |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_fileName method
ms.assetid: a5cb8927-23c6-469e-8f78-f2787d85dba4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a6e871570ad49a4efe2df320f98fe56b5372c6bb
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741807"
---
# <a name="idiasourcefileget_filename"></a>IDiaSourceFile::get_fileName
ソースファイル名を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_fileName ( 
   BSTR* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力ソースファイル名を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
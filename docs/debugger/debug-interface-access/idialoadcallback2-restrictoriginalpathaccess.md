---
title: 'IDiaLoadCallback2:: RestrictOriginalPathAccess |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2::RestrictOriginalPathAccess method
ms.assetid: 31fde3af-2824-4b0f-8d0d-cee6046596f6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6bcdaa7c1896a0ef29706e3650ad8ac56537f778
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742997"
---
# <a name="idialoadcallback2restrictoriginalpathaccess"></a>IDiaLoadCallback2::RestrictOriginalPathAccess
元のデバッグディレクトリで .pdb ファイルを検索することができているかどうかを判断します。

## <a name="syntax"></a>構文

```C++
HRESULT RestrictOriginalPathAccess ();
```

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 @No__t_0 以外のリターンコードは、元のデバッグディレクトリで .pdb ファイルを検索できません。 元のデバッグディレクトリは、デバッグを有効にしたときに実行可能ファイルにコンパイルされたシンボルファイルへのパスです。 このパスは、必ずしも実行可能ファイルが存在するパスと同じではありません。

## <a name="see-also"></a>関連項目
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)
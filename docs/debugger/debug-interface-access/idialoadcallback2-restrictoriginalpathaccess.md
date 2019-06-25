---
title: Idialoadcallback 2::restrictoriginalpathaccess |Microsoft Docs
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
ms.openlocfilehash: 26539d4217682b4d5357f13e9f9368c81297da78
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839746"
---
# <a name="idialoadcallback2restrictoriginalpathaccess"></a>IDiaLoadCallback2::RestrictOriginalPathAccess
元のデバッグ ディレクトリに .pdb ファイルを検索する問題であるかを決定します。

## <a name="syntax"></a>構文

```C++
HRESULT RestrictOriginalPathAccess ();
```

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 すべてのコード以外のリターン`S_OK`元のデバッグ ディレクトリに .pdb ファイルを検索できないようにします。 元のデバッグ ディレクトリは、デバッグがオンにすると、実行可能ファイルにコンパイル シンボル ファイルへのパスです。 このパスが必ずしも同じ実行可能ファイルが存在するパスです。

## <a name="see-also"></a>関連項目
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)
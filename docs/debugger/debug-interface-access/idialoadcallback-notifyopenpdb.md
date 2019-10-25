---
title: 'IDiaLoadCallback:: NotifyOpenPDB |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::NotifyOpenPDB method
ms.assetid: c0547f99-8468-4e57-82ca-9ef7d6707c8a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cbcf8aff8dc18776cbcb09a5fa3f13edca4cd7a7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743064"
---
# <a name="idialoadcallbacknotifyopenpdb"></a>IDiaLoadCallback::NotifyOpenPDB
対象の .pdb ファイルが開かれたときに呼び出されます。

## <a name="syntax"></a>構文

```C++
HRESULT NotifyOpenPDB ( 
   LPCOLESTR pdbPath,
   HRESULT   resultCode
);
```

#### <a name="parameters"></a>パラメーター
 `pdbPath`

から.Pdb ファイルの完全パス。

 `resultCode`

からこのファイルに適用されている読み込みの成功 (`S_OK`) または失敗を示すコード。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 通常、リターンコードは無視されます。

## <a name="see-also"></a>関連項目
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)
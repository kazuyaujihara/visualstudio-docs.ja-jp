---
title: 'IDiaSymbol:: get_builtInKind |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 953e6dba-582e-4b76-b736-898b92e5693e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 183e4da9eebb1a6b26bceb38a3f00a5a64864c8a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740891"
---
# <a name="idiasymbolget_builtinkind"></a>IDiaSymbol::get_builtInKind
HLSL 型の組み込みの種類を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_buildInKind(
   DWORD* pRetVal);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力HLSL 型の組み込みの種類を保持する `DWORD` へのポインター。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
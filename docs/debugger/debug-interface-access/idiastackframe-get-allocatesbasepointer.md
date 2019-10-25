---
title: 'IDiaStackFrame:: get_allocatesBasePointer |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_allocatesBasePointer
ms.assetid: a91e9c8e-c5e3-4887-a60b-f03b5a98f30c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6710a20bb5a01d3d342c31b48f1f96e7e2a2062a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741763"
---
# <a name="idiastackframeget_allocatesbasepointer"></a>IDiaStackFrame::get_allocatesBasePointer
このアドレス範囲内のコードに対してベースポインターが割り当てられているかどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_allocatesBasePointer ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力このフレーム内のコードに対してベースポインターが割り当てられている場合は `TRUE` を返します。それ以外の場合は `FALSE` を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 プロパティがサポートされていない場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
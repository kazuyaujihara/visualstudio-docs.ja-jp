---
title: Idiastackframe::get_size |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_size method
ms.assetid: 71e2f5ab-4aa8-4922-aa8a-b7db97ee143c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6728418e848941bb537f5bec4cb4f772c73485c4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62832054"
---
# <a name="idiastackframegetsize"></a>IDiaStackFrame::get_size
(バイト単位) のスタック フレームのサイズを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_size ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]スタック フレームのサイズをバイト単位で返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`プロパティがサポートされていない場合。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
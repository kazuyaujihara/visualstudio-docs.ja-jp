---
title: 'IDiaStackFrame:: get_type |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_type method
ms.assetid: 99daa97b-5c05-455d-bd1e-800762ccf7c9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b9a2a433c33d46215168238e9956ce0427171b24
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741567"
---
# <a name="idiastackframeget_type"></a>IDiaStackFrame::get_type
フレームの種類を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_type ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力[Stackフレーム Typeenum](../../debugger/debug-interface-access/stackframetypeenum.md)列挙型の列挙体から値を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 プロパティがサポートされていない場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
- [StackFrameTypeEnum 列挙型](../../debugger/debug-interface-access/stackframetypeenum.md)